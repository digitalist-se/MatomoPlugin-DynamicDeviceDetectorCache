# DynamicDeviceDetectorCache Plugin for Matomo

## Description

Makes device detection in Matomo faster by having cached entries for recently seen user agents.

By default, Matomo runs thousands of regular expressions for each tracking request to detect what Browser, Device, Operating system, ... is being used and to detect if a user agent is a bot or not.

This plugin changes this by first looking if a cached result exists for the particular user agent and if so, directly loads the result from the cache.
The difference to the existing `DeviceDetectorCache` plugin is that this plugin doesn't need any setup. No need to learn user agents
from a log file.

For us, this speeds up the tracking request by a factor of 5x.

### How to set it up

You should be using redis for caching. The plugin might also work with file based caching, but we have not tested that.

#### Config setup

You can configure these values in your `config/config.ini.php`

```
[DynamicDeviceDetectorCache]
cache_ttl_in_seconds = 300
```

## Credits

* [Original DeviceDetectorCache plugin](https://github.com/matomo-org/plugin-DeviceDetectorCache)
* [PHP Device Detector library](https://github.com/matomo-org/device-detector/)
* [Matomo - Open Source Web Analytics](https://matomo.org)
