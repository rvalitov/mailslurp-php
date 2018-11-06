# Swagger\Client\AccountControllerApi

All URIs are relative to *https://api.mailslurp.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**createSubscriptionUsingPOST**](AccountControllerApi.md#createSubscriptionUsingPOST) | **POST** /subscription | Upgrade a user to paid
[**getAccountsUsingGET**](AccountControllerApi.md#getAccountsUsingGET) | **GET** /accounts | List available account types


# **createSubscriptionUsingPOST**
> \Swagger\Client\Model\UserDto createSubscriptionUsingPOST($jwt_token, $stripe_token)

Upgrade a user to paid

For use in dashboard

### Example
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

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **jwt_token** | **string**| Cognito ID obtained during login |
 **stripe_token** | **string**| Stripe user payment confirmation token |

### Return type

[**\Swagger\Client\Model\UserDto**](../Model/UserDto.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getAccountsUsingGET**
> \Swagger\Client\Model\AccountsDto getAccountsUsingGET()

List available account types

For use in dashboard

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\AccountControllerApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->getAccountsUsingGET();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountControllerApi->getAccountsUsingGET: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**\Swagger\Client\Model\AccountsDto**](../Model/AccountsDto.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

