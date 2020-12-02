# Badgecollection

Travis
[![Build Status](https://travis-ci.org/slistrom/bth-ram-module.svg?branch=main)](https://travis-ci.org/slistrom/bth-ram-module)

Circle CI
[![CircleCI](https://circleci.com/gh/slistrom/bth-ram-module.svg?style=svg)](https://circleci.com/gh/slistrom/bth-ram-module)

Scrutinizer
[![Build Status](https://scrutinizer-ci.com/g/slistrom/bth-ram-module/badges/build.png?b=main)](https://scrutinizer-ci.com/g/slistrom/bth-ram-module/build-status/main)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/slistrom/bth-ram-module/badges/quality-score.png?b=main)](https://scrutinizer-ci.com/g/slistrom/bth-ram-module/?branch=main)
[![Code Coverage](https://scrutinizer-ci.com/g/slistrom/bth-ram-module/badges/coverage.png?b=main)](https://scrutinizer-ci.com/g/slistrom/bth-ram-module/?branch=main)

# IP and weather module built for Anax

This repository is a module build for the [Anax](https://github.com/canax) framework.
 
## Installation

This repository is available as a package on [Packagist](https://packagist.org/packages/lii/weather).

To install it you need to have Anax installed already. In the Anax root directory run the following commands:

```composer require lii/weather``` to install the module.

While you are still in the Anax root directory you also need to copy certain files to Anax:
```
rsync -av vendor/lii/weather/config/ ./config/
rsync -av vendor/lii/weather/view/ ./view/
rsync -av vendor/lii/weather/src/ ./src/
rsync -av vendor/lii/weather/test/ ./test/
```

This will copy the needed files into the Anax framework.

Once that is done you need to add the namespace for the module files to Anax. Update your composer with the following:
```
"psr-4": {
    "Anax\\": "src/",
    "Lii\\": "src/"
}
```

Run `dump autoloader` in the root directory to load the new namespace.

You also need to update the api_keys_sample file under /config with your own API keys for the IP and weather services to work.

Once all above is done you can use the routes for the module and enjoy the services. The following routes are added by this service.

```
/ip
/api
/weather
```

If you already have cache files from earlier you might have to clean the cache directory.
```make clean-cache```
 