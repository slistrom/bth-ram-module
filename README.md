# IP and weather module built for Anax

This repository is a module build for the [Anax](https://github.com/canax) framework.
 
## Installation

This repository is available as a package on [Packagist](https://packagist.org/packages/lii/weather).

To install it you need to have Anax installed already. In the Anax root directory run the following commands:
```
rsync -av vendor/lii/weather/config/ ./config/
rsync -av vendor/lii/weather/src/ ./src/
rsync -av vendor/lii/weather/test/ ./test/
rsync -av vendor/lii/weather/view/ ./view/
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

Once all above is done you can use the rountes for the module and enjoy the services. The following routes are added by this service.

/ip

/api

/weather
