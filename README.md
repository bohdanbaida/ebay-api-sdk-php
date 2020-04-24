# EBAY-API-SDK-PHP

This project is based on [Ebay SDK](https://github.com/davidtsadler/ebay-sdk-php) written by David T. Sadler to make up for the lack of an official SDK for PHP.
(It is in no way endorsed, sponsored or maintained by eBay).

After original repository was archived, and no longer supported, I've created this repository from copy of [Ebay SDK](https://github.com/davidtsadler/ebay-sdk-php). To keep improving and maintaining SDK for eBay API.

This project enables PHP developers to use the [eBay API](https://go.developer.ebay.com/api-documentation) in their PHP code, and build software using services such as [Finding](http://developer.ebay.com/Devzone/finding/Concepts/FindingAPIGuide.html), [Trading](http://developer.ebay.com/DevZone/guides/ebayfeatures/index.html), [Shopping](http://developer.ebay.com/Devzone/shopping/docs/Concepts/ShoppingAPIGuide.html), etc. You can get started by [installing the SDK via Composer](http://devbay.net/sdk/guides/getting-started/installation.html) and by following the [Basic Usage Guide](http://devbay.net/sdk/guides/getting-started/basic-usage.html).

This is a personal project that has been maintained by me, [Bohdan B.](http://twitter.com/bosston812), to make work for PHP developer with eBay API more efficient.

## Features

  - Compatible with PHP 5.5 or greater.
  - Easy to install with [Composer](http://getcomposer.org/).
  - Compliant with [PSR-1](http://www.php-fig.org/psr/psr-1/), [PSR-2](http://www.php-fig.org/psr/psr-2/) and [PSR-4](http://www.php-fig.org/psr/psr-4/).

## Resources

  - [User Guides](http://devbay.net/sdk/guides/) - Getting started guide and in-depth information.
  - [Examples](https://github.com/davidtsadler/ebay-sdk-examples) - Several examples of using the SDK.
  - [@bosston812](https://twitter.com/bosston812) - Follow on Twitter for announcements of releases, important changes and so on.

## Requirements

  - PHP 5.5 or greater with the following extensions:
      - cURL
      - libxml
  - 64 bit version of PHP recommended as there are some [issues when using the SDK with 32 bit](http://devbay.net/sdk/guides/getting-started/requirements.html#using-the-sdk-with-32-bit-systems).
  - SSL enabled on the cURL extension so that https requests can be made.

## Installation

  1. Install Composer.

     ```
     curl -sS https://getcomposer.org/installer | php
     ```

  1. Install the SDK.

     ```
     php composer.phar require bosston812/ebay-api-sdk-php
     ```

  1. Require Composer's autoloader by adding the following line to your code.

     ```php
     require 'vendor/autoload.php';
     ```

## Example

### Get the official eBay time

```php
<?php

require 'vendor/autoload.php';

use \DTS\eBaySDK\Shopping\Services;
use \DTS\eBaySDK\Shopping\Types;

// Create the service object.
$service = new Services\ShoppingService();

// Create the request object.
$request = new Types\GeteBayTimeRequestType();

// Send the request to the service operation.
$response = $service->geteBayTime($request);

// Output the result of calling the service operation.
printf("The official eBay time is: %s\n", $response->Timestamp->format('H:i (\G\M\T) \o\n l jS Y'));
```

## Project Goals

  - Be well maintained.

## License

Licensed under the [Apache Public License 2.0](http://www.apache.org/licenses/LICENSE-2.0.html).

Copyright 2020 [Bohdan B.](http://twitter.com/bosston812)
