_this page is under construction as the feature is still under development._

_The feature available since 09 beta 6._

With version 09 RybaFish will provide very basic alerting functionality.

When some predefined value (i.g. {alert}) selected from the DB and displayed in the result set - the alert will be triggered.

The easiest way to demonstrate this is execute:

```SQL
select '{alert}' from dummy;
```
**Note:** the feature is only available if experimental features are enabled.

There are several settings to configure the feature:

```YAML
# uncomment to have experimental stuff (like sql console)
experimental: True

# string that will trigger the alert sound when selected:
alertTriggerOn: '{alert}'

# default sound to play when '{alert}' value selected
alertSound: 'default.wav'

# alert sounds volume
alertVolume: 80

# Popup the window on alert
alertAutoPopup: True
```

Two alert sounds come with RybaFish itelf: default.wav an warning.wav. Those files part of the build and can be used without any additional actions.

If you want to use your own sound you can create 'snd' folder and copy custom sound files there. In this case no path required when you define the alertSound setting.

It is also possible to specificly define the alert sound in the runtime, in this case you need to compose the output string like this:

```SQL
select '{alert:warning}' from dummy;
```

This will play warning.wav and not the default.wav