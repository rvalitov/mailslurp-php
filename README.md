**⚠️ The MailSlurp has now official PHP client, use it https://packagist.org/packages/mailslurp/mailslurp-client-php**

**So this repository is archived.**

![API Version](https://img.shields.io/badge/API-v0.0.1-green.svg?style=flat) ![PHP](https://img.shields.io/badge/PHP-7.0--7.2-green.svg?style=flat)

# MailSlurp-PHP
[MailSlurp](https://www.mailslurp.com) is an end-to-end email testing service. It has a [web-app](https://www.mailslurp.com/dashboard) for managing your account and a [REST API](https://api.mailslurp.com) for sending and receiving emails from randomly generated email addresses.  

## Why? 
MailSlurp was built to test the integration of email services within an app. If your application relies on the sending or receiving of emails, then MailSlurp will let you test that functionality. This is a more common need than you might think: if your app has a sign up process that requires email verification, how do you currently test that?  

## Getting started
 - [API Docs](https://www.mailslurp.com/documentation) 
 - [Code Examples](https://www.mailslurp.com/documentation/examples) 
 - [Swagger Definition](https://api.mailslurp.com/v2/api-docs)  
 
Every API request requires a valid API Key appended as a query parameter. [To obtain an API Key visit your account dashboard](https://www.mailslurp.com/dashboard). 

The general flow is as follows:

- Create a new inbox during a test. The email address will be returned in the apiReponse.
- Send an email to that address or trigger an action in your test that does so.
- Fetch the email for your new inbox and check if its content is what you expected, or use the content in another action.
 
## SDK
- There is an official [Javascript SDK](https://www.npmjs.com/package/mailslurp-client) available on npm. 
- This PHP version was generated from [swagger JSON definition](https://api.mailslurp.com/v2/api-docs) using [swagger-codegen](https://github.com/swagger-api/swagger-codegen) and adapted for use with PHP 7.0+ (see [commits](https://github.com/rvalitov/mailslurp-php/commits/master) for a full list of changes). 

## Legal
The Mailslurp API code is owned by [PettmanUG](http://pettmanug.site) and uses a proprietary [software licence](http://www.binpress.com/license/view/l/c8376a01eca7465027a978d3fde5a1e2). The SDKs are free to use in any project and have an ISC licence.

## Bugs, features, support 
To report bugs or request features please see the [contact page](https://www.mailslurp.com/contact). For help see [support](https://www.mailslurp.com/support).

## Requirements

PHP 7.0 and later

## Installation & Usage
### Composer

To install the bindings via [Composer](http://getcomposer.org/), run command

```bash
composer require rvalitov/mailslurp-php
``` 

Or manually add the following to `composer.json`:

```json
{
  "require": {
    "rvalitov/mailslurp-php": "^0.0.1"
  }
}
```

Then run `composer install`

### Manual Installation

Download the files and include `autoload.php`:

```php
    require_once('/path/to/MailSlurp-PHP/vendor/autoload.php');
```

## Tests
**Note. Tests are not implemented yet!**

To run the unit tests:

```
composer install
./vendor/bin/phpunit
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\AccountControllerApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$jwt_token = "jwt_token_example"; // string | Cognito ID obtained during login
$stripe_token = "stripe_token_example"; // string | Stripe user payment confirmation token

try {
    $result = $apiInstance->createSubscriptionUsingPOST($jwt_token, $stripe_token);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountControllerApi->createSubscriptionUsingPOST: ', $e->getMessage(), PHP_EOL;
}

?>
```

## Documentation for API Endpoints

All URIs are relative to *https://api.mailslurp.com*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AccountControllerApi* | [**createSubscriptionUsingPOST**](docs/Api/AccountControllerApi.md#createsubscriptionusingpost) | **POST** /subscription | Upgrade a user to paid
*AccountControllerApi* | [**getAccountsUsingGET**](docs/Api/AccountControllerApi.md#getaccountsusingget) | **GET** /accounts | List available account types
*InboxControllerApi* | [**createRandomInboxUsingPOST**](docs/Api/InboxControllerApi.md#createrandominboxusingpost) | **POST** /inboxes | Create an inbox
*InboxControllerApi* | [**deleteInboxUsingDELETE**](docs/Api/InboxControllerApi.md#deleteinboxusingdelete) | **DELETE** /inboxes/{uuid} | Delete an inbox
*InboxControllerApi* | [**getEmailsForInboxUsingGET**](docs/Api/InboxControllerApi.md#getemailsforinboxusingget) | **GET** /inboxes/{uuid} | Fetch emails for a given inbox
*InboxControllerApi* | [**getListOfInboxesUsingGET**](docs/Api/InboxControllerApi.md#getlistofinboxesusingget) | **GET** /inboxes | List your inboxes
*InboxControllerApi* | [**sendEmailFromUserUsingPOST**](docs/Api/InboxControllerApi.md#sendemailfromuserusingpost) | **POST** /inboxes/{uuid} | Send an email
*UserControllerApi* | [**getUserUsingGET**](docs/Api/UserControllerApi.md#getuserusingget) | **GET** /user | Fetch a user


## Documentation For Models

 - [AccountDto](docs/Model/AccountDto.md)
 - [AccountsDto](docs/Model/AccountsDto.md)
 - [ApiReponse](docs/Model/ApiReponse.md)
 - [ApiReponseInboxDto_](docs/Model/ApiReponseInboxDto_.md)
 - [ApiReponseListEmailDto_](docs/Model/ApiReponseListEmailDto_.md)
 - [ApiReponseListInboxDto_](docs/Model/ApiReponseListInboxDto_.md)
 - [EmailDto](docs/Model/EmailDto.md)
 - [InboxDto](docs/Model/InboxDto.md)
 - [SendEmailDto](docs/Model/SendEmailDto.md)
 - [UserDto](docs/Model/UserDto.md)


## Documentation For Authorization

 All endpoints do not require authorization.


# Generation from Swagger
If you want to generate the original code from Swagger, use the following commands:

```bash
wget http://central.maven.org/maven2/io/swagger/swagger-codegen-cli/2.3.1/swagger-codegen-cli-2.3.1.jar -O swagger-codegen-cli.jar
java -jar .\swagger-codegen-cli.jar generate -i https://api.mailslurp.com/v2/api-docs -l php -o ./out
```

