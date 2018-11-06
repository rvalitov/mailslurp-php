# Swagger\Client\UserControllerApi

All URIs are relative to *https://api.mailslurp.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**getUserUsingGET**](UserControllerApi.md#getUserUsingGET) | **GET** /user | Fetch a user


# **getUserUsingGET**
> \Swagger\Client\Model\UserDto getUserUsingGET($jwt_token)

Fetch a user

Used by the dashboard to fetch user information.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\UserControllerApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$jwt_token = "jwt_token_example"; // string | Cognito ID obtained during login

try {
    $result = $apiInstance->getUserUsingGET($jwt_token);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UserControllerApi->getUserUsingGET: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **jwt_token** | **string**| Cognito ID obtained during login |

### Return type

[**\Swagger\Client\Model\UserDto**](../Model/UserDto.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

