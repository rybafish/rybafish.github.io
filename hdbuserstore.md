### hdbuserstore

RybaFish does not support hdbuserstore as a password storage mechanism.

However, if you are using hdbuserstore on the same machine for any reason, it is possible to export a single configuration from RybaFish to hdbuserstore.

To do this, open the connection dialog (Alt+C), select the required configuration, and press Ctrl+F12.

This will trigger a command similar to the following:

```
hdbuserstore -i set "cfgname" "host:port" "username"
```

The password will be passed in the background automatically.

The result will be shown in the dialog status line. For detailed information, refer to the rybafish.log file.

You need RybaFish 097 beta vi to use this feature.
