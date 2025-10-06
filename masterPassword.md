
**Note:** this is just a <span style="color:red">draught documentation page</span>, the feature is not released yet even for beta usage.

## Why Master Password

If you don’t set a master password, RybaFish still encodes stored passwords — but it uses a generic algorithm, meaning any RybaFish can decode them. If your connections.yaml file is compromised, attackers will have access to your passwords.

When you set a master password, RybaFish derives a unique encryption key from it. Without this master password, it’s impossible to decrypt stored passwords.

This provides a proper level of security for stored passwords. Using a master password is the recommended setup, especially in shared environments such as virtual machines or multi-user systems.

## How It Works

All connection-related data is stored in the connections.yaml file.

Passwords are stored in the "pwd" field of each connection entry.
In old versions this value was stored as a binary string — so if you needed to use it manually, you had to Base64-decode it.
Starting with 0.96 beta V, passwords are stored as plain text (encoded, but without additional binary encoding).

If you choose to use a master password, connections.yaml will also contain a `__salt__` value.
This is a 32-byte hexadecimal string used to make the encoded passwords unique to your RybaFish instance and to make brute-force attacks more difficult.

If you choose not to use a master password, this value will be explicitly set to an empty string.

## How To Not Use It, Please?

Option one is just reply "Don't set" when RybaFish asks for master password for the first time.

Option two is manually adjust connections.yaml and set `__salt__: ''` which should be equal to option one.

Option three is set `disableMasterPassword: True` in config.yaml

**Note again:** this is just a <span style="color:red">draught documentation page</span>, the feature is not released yet even for beta usage.
