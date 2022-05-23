# Overview

**Before we start**

**Limitation:** Variable names **or values** cannot contain coma characters. Never. This will brake parsing. But... there are replacements possible, see below.

**Okay, now start**

Starting 091 beta 1 (not released yet) RybaFish supports "variables" in custom KPIs.

Variables are placeholders that will be replaced by actual values before usage. Variables defined in the custom KPI yaml file. Let's take [expensive statements](/customKPIgantt) custom KPI definition exp_st.yaml and add variables:

```
variables: 'y1: 10, y2: 50, threshold: 30, user: %'
```

All variables listed in a single string in JSON-like format. This particular line defines four variables: y1, y2, threshhold and user.

Variables can be used in the **same** file for dynamic values substitution. Usage example:

```
...

description: 'Expensive Statements > $threshold s'}
```

When used in the KPI definition variables must be prefixed with $ character. Considering the definition above, actual usage will be translated to:
```
...

description: 'Expensive Statements > 30 s'}
```

# RybaFish Runtime
During the usage of RybaFish you can change variables in the KPI Table last column. Initial values are loaded from the KPI definition file.

There is also a dialog that combines variables for all the custom KPIs: menu -> Variables, or Alt+V.

On exit values will be stored in the layout.yaml file, so the next time you start RybaFish you continue working with the same values.

When one variable deleted from this definition - the default value from the KPI definition will be used.

When the whole Variables cell deleted - the default definition will be loaded from the KPI definition file. Explicit 'Reset to defaults' option is available in Alt+V dialog.

# Replacements
Okay, but what if we want to define a list of values for a specific variable? For example, we only want to get expensive statements for a list of specific user. Something which result in statement likw `select ... where db_user in ('SASCHA','LUCIA')`. Naturally, we will try to do the following:

```
variables: 'y1: 10, y2: 50, threshold: 30, userlist: 'SASCHA','LUCIA''
```
But this is not going to work to two reasons. First - comas are allowed only to separate variables. Second - quotes are requred to generate correct SQL but this will brake parsing of yaml file.

To overcome this limitation there is an option to replace characters in variables:
```
variablesReplace: [";", "','"]
```

This means every `;` character inside the variable will be replaced by the ```','``` sequence. We also need to adjust variables definition:
```
variables: 'y1: 10, y2: 50, threshold: 30, userlist: SASCHA;LUCIA'
variablesReplace: [";", "','"]
```

And in the sql statement definition now we can use this (note the quotes around the variable, this is requred to compensate missing ones in the variable):
```
sql> ...
    where ...
       and db_user in ('$userlist')
```
which will be translated to:
```
sql> ...
    where ...
       and db_user in ('SASCHA','LUCIA')
```


# Troubleshooting
If something unusual or not clear happens to variables usage you can:
* open the config.yaml, set the loglevel to 5
* reload the config (Actions -> Reload config)
* reproduce the issue and check the .log file, may be you will be able to see unexpected variables values or something like that

One more way to reset things to defaults is just deleta variables definition in KPIs table, set it to empty string. This should reset variables do the defaults defined in custom KPI yaml file.

And anothe one:
* stop RybaFish
* delete "variables" from the layout.yaml
* start the tool again

By doing so you reload default values from the custom KPI file definition so hopefuly you get th eexpected values.
