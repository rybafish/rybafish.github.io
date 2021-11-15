_this page is under construction as the feature is still under development._

_The feature available since 09 beta 6._

With version 09 RybaFish will provide very basic alerting functionality.

When some predefined value (i.g. {alert}) selected from the DB and displayed in the result set - the alert will be triggered.

There are several settings to configure the feature.

```
# string that will trigger the alert sound when selected:
alertTriggerOn: '{alert}'

# default sound to play when '{alert}' value selected
alertSound: 'default.wav'

# alert sounds volume
alertVolume: 80

# Popup the window on alert
alertAutoPopup: True
```
