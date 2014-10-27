# OAuth wrapper for Laravel 4

oauth-4-laravel is a simple laravel 4 service provider (wrapper) for [Phpvirus/Oauth](https://github.com/shamimhasan/PHP-oAuth) 
which provides oAuth support in PHP 5.3+ and is very easy to integrate with any project which requires an oAuth client.

---
 
- [Supported services](#supported-services)
- [Installation](#installation)
- [Registering the Package](#registering-the-package)
- [Configuration](#configuration)
- [Usage](#usage)
- [Basic usage](#basic-usage)
- [More usage examples](#more-usage-examples)

## Supported services

The library supports both oAuth 1.x and oAuth 2.0 compliant services. A list of currently implemented services can be found below. More services will be implemented soon.

Included service implementations:

 - OAuth1
    - BitBucket
    - Etsy
    - FitBit
    - Flickr
    - Scoop.it!
    - Tumblr
    - Twitter
    - Xing
    - Yahoo
 - OAuth2
    - Amazon
    - BitLy
    - Box
    - Dailymotion
    - Dropbox
    - Facebook
    - Foursquare
    - GitHub
    - Google
    - Harvest
    - Heroku
    - Instagram
    - LinkedIn
    - Mailchimp
    - Microsoft
    - PayPal
    - Pocket
    - Reddit
    - RunKeeper
    - SoundCloud
	- Stripe
    - Vkontakte
    - Yammer
- more to come!

To learn more about Phpvirus/Oauth go [here](https://github.com/shamimhasan/PHP-oAuth) 

## Installation

This library can be found on [Packagist](https://packagist.org/packages/phpvirus/oauth).
The recommended way to install this is through [composer](http://getcomposer.org).

Add oauth-4-laravel to your composer.json file:

```
"require": {
	"phpvirus/oauth": "0.1.*@dev",
	"darkvirus/oauth-4-laravel": "dev-master"
}
```

And install dependencies:

```bash
$ curl -sS https://getcomposer.org/installer | php
$ php composer.phar install
```


Or Use composer to install this package.

```
$ composer update
```

### Registering the Package

Register the service provider within the ```providers``` array found in ```app/config/app.php```:

```php
'providers' => array(
	// ...
	
	'Darkvirus\OAuth\OAuthServiceProvider'
)
```

Add an alias within the ```aliases``` array found in ```app/config/app.php```:


```php
'aliases' => array(
	// ...
	
	'OAuth' => 'Darkvirus\OAuth\Facade\OAuth',
)
```

## Configuration

There are two ways to configure oauth-4-laravel.
You can choose the most convenient way for you. 
You can use package config file which can be 
generated through command line by artisan (option 1) or 
you can simply create a config file called ``oauth-4-laravel.php`` in 
your ``app\config\`` directory (option 2).

#### Option 1

Create configuration file for package using artisan command

```
$ php artisan config:publish darkvirus/oauth-4-laravel
```

#### Option 2

Create configuration file manually in config directory ``app/config/oauth-4-laravel.php`` and put there code from below.

```php
<?php
return array( 
	
	/*
	|--------------------------------------------------------------------------
	| oAuth Config
	|--------------------------------------------------------------------------
	*/

	/**
	 * Storage
	 */
	'storage' => 'Session', 

	/**
	 * Consumers
	 */
	'consumers' => array(

		/**
		 * Stripe
		 */
		'Stripe' => array(
            'client_id' => '',
            'client_secret' => '',
        ),		

	)

);
```
