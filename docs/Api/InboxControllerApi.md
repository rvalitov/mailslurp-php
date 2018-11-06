# Swagger\Client\InboxControllerApi

All URIs are relative to *https://api.mailslurp.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**createRandomInboxUsingPOST**](InboxControllerApi.md#createRandomInboxUsingPOST) | **POST** /inboxes | Create an inbox
[**deleteInboxUsingDELETE**](InboxControllerApi.md#deleteInboxUsingDELETE) | **DELETE** /inboxes/{uuid} | Delete an inbox
[**getEmailsForInboxUsingGET**](InboxControllerApi.md#getEmailsForInboxUsingGET) | **GET** /inboxes/{uuid} | Fetch emails for a given inbox
[**getListOfInboxesUsingGET**](InboxControllerApi.md#getListOfInboxesUsingGET) | **GET** /inboxes | List your inboxes
[**sendEmailFromUserUsingPOST**](InboxControllerApi.md#sendEmailFromUserUsingPOST) | **POST** /inboxes/{uuid} | Send an email


# **createRandomInboxUsingPOST**
> \Swagger\Client\Model\ApiReponseInboxDto_ createRandomInboxUsingPOST($api_key)

Create an inbox

Create a new random inbox and return the id and email address for it. Send emails to this address and they will be stored for this inbox.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\InboxControllerApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$api_key = "test"; // string | Your API Key. Sign up and find it in your dashboard.

try {
    $result = $apiInstance->createRandomInboxUsingPOST($api_key);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboxControllerApi->createRandomInboxUsingPOST: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **api_key** | **string**| Your API Key. Sign up and find it in your dashboard. | [default to test]

### Return type

[**\Swagger\Client\Model\ApiReponseInboxDto_**](../Model/ApiReponseInboxDto_.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **deleteInboxUsingDELETE**
> \Swagger\Client\Model\ApiReponse deleteInboxUsingDELETE($api_key, $uuid)

Delete an inbox

Delete an inbox and all the emails associated with it.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\InboxControllerApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$api_key = "test"; // string | Your API Key. Sign up and find it in your dashboard.
$uuid = "uuid_example"; // string | The inbox's id.

try {
    $result = $apiInstance->deleteInboxUsingDELETE($api_key, $uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboxControllerApi->deleteInboxUsingDELETE: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **api_key** | **string**| Your API Key. Sign up and find it in your dashboard. | [default to test]
 **uuid** | **string**| The inbox&#39;s id. |

### Return type

[**\Swagger\Client\Model\ApiReponse**](../Model/ApiReponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getEmailsForInboxUsingGET**
> \Swagger\Client\Model\ApiReponseListEmailDto_ getEmailsForInboxUsingGET($api_key, $uuid, $min_count, $max_wait, $since)

Fetch emails for a given inbox

Return a list of emails stored in a given inbox. Each email contains various properties including the email body (in eml format), subject, and sender. The `since` parameter is a ISO8601 LocalDateTime that will filter for emails received on or after the given DateTime. Note that because an inbox may take 5 to 10 seconds to receive an email, you can use the `waitFor` parameter to hold a request open until the desired number of emails is present. If this number is not met after 100 seconds, an error will be returned.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\InboxControllerApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$api_key = "test"; // string | Your API Key. Sign up and find it in your dashboard.
$uuid = "uuid_example"; // string | The inbox's id.
$min_count = 56; // int | Wait a maximum of 100 seconds for atleast this many emails in an inbox before returning a result.
$max_wait = 789; // int | Maximum seconds API should spend retrying your inbox until the minCount is satisfied
$since = new \DateTime("2013-10-20T19:20:30+01:00"); // \DateTime | Filter for emails received on or after this ISO8601 LocalDateTime.

try {
    $result = $apiInstance->getEmailsForInboxUsingGET($api_key, $uuid, $min_count, $max_wait, $since);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboxControllerApi->getEmailsForInboxUsingGET: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **api_key** | **string**| Your API Key. Sign up and find it in your dashboard. | [default to test]
 **uuid** | **string**| The inbox&#39;s id. |
 **min_count** | **int**| Wait a maximum of 100 seconds for atleast this many emails in an inbox before returning a result. | [optional]
 **max_wait** | **int**| Maximum seconds API should spend retrying your inbox until the minCount is satisfied | [optional]
 **since** | **\DateTime**| Filter for emails received on or after this ISO8601 LocalDateTime. | [optional]

### Return type

[**\Swagger\Client\Model\ApiReponseListEmailDto_**](../Model/ApiReponseListEmailDto_.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getListOfInboxesUsingGET**
> \Swagger\Client\Model\ApiReponseListInboxDto_ getListOfInboxesUsingGET($api_key)

List your inboxes

Return a list of your inboxes. Each inbox has a uuid and an email address. Emails sent to the email address are stored in the inbox and can be fetched via `/inboxes/{uuid}`.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\InboxControllerApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$api_key = "test"; // string | Your API Key. Sign up and find it in your dashboard.

try {
    $result = $apiInstance->getListOfInboxesUsingGET($api_key);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboxControllerApi->getListOfInboxesUsingGET: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **api_key** | **string**| Your API Key. Sign up and find it in your dashboard. | [default to test]

### Return type

[**\Swagger\Client\Model\ApiReponseListInboxDto_**](../Model/ApiReponseListInboxDto_.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **sendEmailFromUserUsingPOST**
> \Swagger\Client\Model\ApiReponse sendEmailFromUserUsingPOST($api_key, $uuid, $send_email_dto)

Send an email

Send an email from the given inbox's email address. Useful if you need to test a user contacting you, for instance.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\InboxControllerApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$api_key = "test"; // string | Your API Key. Sign up and find it in your dashboard.
$uuid = "uuid_example"; // string | The inbox's id.
$send_email_dto = new \Swagger\Client\Model\SendEmailDto(); // \Swagger\Client\Model\SendEmailDto | The email to send.

try {
    $result = $apiInstance->sendEmailFromUserUsingPOST($api_key, $uuid, $send_email_dto);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboxControllerApi->sendEmailFromUserUsingPOST: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **api_key** | **string**| Your API Key. Sign up and find it in your dashboard. | [default to test]
 **uuid** | **string**| The inbox&#39;s id. |
 **send_email_dto** | [**\Swagger\Client\Model\SendEmailDto**](../Model/SendEmailDto.md)| The email to send. |

### Return type

[**\Swagger\Client\Model\ApiReponse**](../Model/ApiReponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

