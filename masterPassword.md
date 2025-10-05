## Why Master Password
TBD

## How It Works
If you don't have a master-password RybaFish still stores passwords encoded, but with generic alghorithm so RybaFish instance can decode it.

If you have chosen to use master-password, RybaFish will encode passwords using a specific derived key, so without this master-password it is not possible to decode the contents of connections.yaml.

## connections.yaml
pwd is base64 encoded to have it in yaml so if you intend to manually decrypt it you need to base64.decode() it before decrypting.
