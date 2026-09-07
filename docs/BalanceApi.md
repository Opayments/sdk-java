# BalanceApi

All URIs are relative to *https://api.opayments.io/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getBalance**](BalanceApi.md#getBalance) | **GET** /balance | Получить баланс |
| [**getBalanceWithHttpInfo**](BalanceApi.md#getBalanceWithHttpInfo) | **GET** /balance | Получить баланс |



## getBalance

> Balance getBalance()

Получить баланс

Возвращает текущий баланс проекта.

### Example

```java
// Import classes:
import io.opayments.sdk.ApiClient;
import io.opayments.sdk.ApiException;
import io.opayments.sdk.Configuration;
import io.opayments.sdk.auth.*;
import io.opayments.sdk.models.*;
import io.opayments.sdk.api.BalanceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.opayments.io/api/v1");
        
        // Configure API key authorization: RequestSignature
        ApiKeyAuth RequestSignature = (ApiKeyAuth) defaultClient.getAuthentication("RequestSignature");
        RequestSignature.setApiKey("YOUR API KEY");
        // Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
        //RequestSignature.setApiKeyPrefix("Token");

        // Configure API key authorization: ProjectIdentity
        ApiKeyAuth ProjectIdentity = (ApiKeyAuth) defaultClient.getAuthentication("ProjectIdentity");
        ProjectIdentity.setApiKey("YOUR API KEY");
        // Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
        //ProjectIdentity.setApiKeyPrefix("Token");

        BalanceApi apiInstance = new BalanceApi(defaultClient);
        try {
            Balance result = apiInstance.getBalance();
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling BalanceApi#getBalance");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Reason: " + e.getResponseBody());
            System.err.println("Response headers: " + e.getResponseHeaders());
            e.printStackTrace();
        }
    }
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**Balance**](Balance.md)


### Authorization

[RequestSignature](../README.md#RequestSignature), [ProjectIdentity](../README.md#ProjectIdentity)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Баланс проекта. |  * X-Request-Id -  <br>  |
| **400** | Некорректные параметры запроса. |  * X-Request-Id -  <br>  |
| **401** | Не пройдена аутентификация или проверка подписи. |  * X-Request-Id -  <br>  |
| **429** | Превышен лимит запросов. |  * X-Request-Id -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset - Unix-время сброса лимита. <br>  * Retry-After -  <br>  |
| **503** | Сервис временно недоступен. |  * X-Request-Id -  <br>  |

## getBalanceWithHttpInfo

> ApiResponse<Balance> getBalanceWithHttpInfo()

Получить баланс

Возвращает текущий баланс проекта.

### Example

```java
// Import classes:
import io.opayments.sdk.ApiClient;
import io.opayments.sdk.ApiException;
import io.opayments.sdk.ApiResponse;
import io.opayments.sdk.Configuration;
import io.opayments.sdk.auth.*;
import io.opayments.sdk.models.*;
import io.opayments.sdk.api.BalanceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.opayments.io/api/v1");
        
        // Configure API key authorization: RequestSignature
        ApiKeyAuth RequestSignature = (ApiKeyAuth) defaultClient.getAuthentication("RequestSignature");
        RequestSignature.setApiKey("YOUR API KEY");
        // Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
        //RequestSignature.setApiKeyPrefix("Token");

        // Configure API key authorization: ProjectIdentity
        ApiKeyAuth ProjectIdentity = (ApiKeyAuth) defaultClient.getAuthentication("ProjectIdentity");
        ProjectIdentity.setApiKey("YOUR API KEY");
        // Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
        //ProjectIdentity.setApiKeyPrefix("Token");

        BalanceApi apiInstance = new BalanceApi(defaultClient);
        try {
            ApiResponse<Balance> response = apiInstance.getBalanceWithHttpInfo();
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling BalanceApi#getBalance");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Response headers: " + e.getResponseHeaders());
            System.err.println("Reason: " + e.getResponseBody());
            e.printStackTrace();
        }
    }
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

ApiResponse<[**Balance**](Balance.md)>


### Authorization

[RequestSignature](../README.md#RequestSignature), [ProjectIdentity](../README.md#ProjectIdentity)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Баланс проекта. |  * X-Request-Id -  <br>  |
| **400** | Некорректные параметры запроса. |  * X-Request-Id -  <br>  |
| **401** | Не пройдена аутентификация или проверка подписи. |  * X-Request-Id -  <br>  |
| **429** | Превышен лимит запросов. |  * X-Request-Id -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset - Unix-время сброса лимита. <br>  * Retry-After -  <br>  |
| **503** | Сервис временно недоступен. |  * X-Request-Id -  <br>  |

