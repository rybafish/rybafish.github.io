# [DRAFT] Overview

**Before we start**

**Limitation:** Variable names or values cannot contain coma characters. This will brake parsing.

**Okay, start**

Starting 09 beta 2 RybaFish supports "variables" in custom KPIs.

Variables are placeholders that will be replaced by actual values before usage. Variables defined in the custom KPI yaml file, for example:

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

Currently only following KPI definition areas considered:

* kpis.y_range
* kpis.label
* kpis.description
* sql

# RybaFish Runtime
During usage of RybaFish you can change variables in the KPI Table last column. Initial values are loaded from the KPI definition file.

On exit values will be stored in the layout.yaml file, so the next time you start RybaFish you continue working with the same values.

When one variable deleted from this definition - the default value from the KPI definition will be used.

When the whole Variables cell deleted - the default definition will be loaded from the KPI definition file. 

# Troubleshooting
If something unusual or not clear happens to variables usage you can:
* open the config.yaml, set the loglevel to 5
* reload the config (Actions -> Reload config)
* reproduce the issue and check the .log file, may be you will be able to see unexpected variables values or something like that

The other option is:
* stop RybaFish
* delete "variables" from the layout.yaml
* start the tool again

By doing so you reload default values from the custom KPI file definition so hopefuly you get th eexpected values.
