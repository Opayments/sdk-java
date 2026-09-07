# RefundsApi

All URIs are relative to *https://api.opayments.io/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createPaymentRefund**](RefundsApi.md#createPaymentRefund) | **POST** /payments/{paymentId}/refund | Создать возврат |
| [**createPaymentRefundWithHttpInfo**](RefundsApi.md#createPaymentRefundWithHttpInfo) | **POST** /payments/{paymentId}/refund | Создать возврат |
| [**getPaymentRefund**](RefundsApi.md#getPaymentRefund) | **GET** /payments/{paymentId}/refund | Получить возврат |
| [**getPaymentRefundWithHttpInfo**](RefundsApi.md#getPaymentRefundWithHttpInfo) | **GET** /payments/{paymentId}/refund | Получить возврат |



## createPaymentRefund

> Refund createPaymentRefund(paymentId, createRefundRequest)

Создать возврат

### Example

```java
// Import classes:
import io.opayments.sdk.ApiClient;
import io.opayments.sdk.ApiException;
import io.opayments.sdk.Configuration;
import io.opayments.sdk.auth.*;
import io.opayments.sdk.models.*;
import io.opayments.sdk.api.RefundsApi;

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

        RefundsApi apiInstance = new RefundsApi(defaultClient);
        UUID paymentId = UUID.fromString("c9ee7c85-4cc0-494f-a0de-0af7257a66a6"); // UUID | 
        CreateRefundRequest createRefundRequest = new CreateRefundRequest(); // CreateRefundRequest | 
        try {
            Refund result = apiInstance.createPaymentRefund(paymentId, createRefundRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling RefundsApi#createPaymentRefund");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Reason: " + e.getResponseBody());
            System.err.println("Response headers: " + e.getResponseHeaders());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **paymentId** | **UUID**|  | |
| **createRefundRequest** | [**CreateRefundRequest**](CreateRefundRequest.md)|  | |

### Return type

[**Refund**](Refund.md)


### Authorization

[RequestSignature](../README.md#RequestSignature), [ProjectIdentity](../README.md#ProjectIdentity)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Ранее созданный возврат с теми же параметрами. |  * Location -  <br>  * X-Request-Id -  <br>  |
| **202** | Возврат принят в обработку. |  * Location -  <br>  * X-Request-Id -  <br>  |
| **400** | Некорректные параметры запроса. |  * X-Request-Id -  <br>  |
| **401** | Не пройдена аутентификация или проверка подписи. |  * X-Request-Id -  <br>  |
| **404** | Ресурс не найден. |  * X-Request-Id -  <br>  |
| **409** | Параметры ранее созданного возврата отличаются. |  * X-Request-Id -  <br>  |
| **415** | Тело запроса должно быть JSON. |  * X-Request-Id -  <br>  |
| **422** | Операция невозможна в текущем статусе платежа. |  * X-Request-Id -  <br>  |
| **429** | Превышен лимит запросов. |  * X-Request-Id -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset - Unix-время сброса лимита. <br>  * Retry-After -  <br>  |
| **500** | Внутренняя ошибка сервиса. |  * X-Request-Id -  <br>  |
| **502** | Внешний сервис вернул некорректный ответ. |  * X-Request-Id -  <br>  |
| **503** | Сервис временно недоступен. |  * X-Request-Id -  <br>  |
| **504** | Внешний сервис не ответил вовремя. |  * X-Request-Id -  <br>  |

## createPaymentRefundWithHttpInfo

> ApiResponse<Refund> createPaymentRefundWithHttpInfo(paymentId, createRefundRequest)

Создать возврат

### Example

```java
// Import classes:
import io.opayments.sdk.ApiClient;
import io.opayments.sdk.ApiException;
import io.opayments.sdk.ApiResponse;
import io.opayments.sdk.Configuration;
import io.opayments.sdk.auth.*;
import io.opayments.sdk.models.*;
import io.opayments.sdk.api.RefundsApi;

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

        RefundsApi apiInstance = new RefundsApi(defaultClient);
        UUID paymentId = UUID.fromString("c9ee7c85-4cc0-494f-a0de-0af7257a66a6"); // UUID | 
        CreateRefundRequest createRefundRequest = new CreateRefundRequest(); // CreateRefundRequest | 
        try {
            ApiResponse<Refund> response = apiInstance.createPaymentRefundWithHttpInfo(paymentId, createRefundRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling RefundsApi#createPaymentRefund");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Response headers: " + e.getResponseHeaders());
            System.err.println("Reason: " + e.getResponseBody());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **paymentId** | **UUID**|  | |
| **createRefundRequest** | [**CreateRefundRequest**](CreateRefundRequest.md)|  | |

### Return type

ApiResponse<[**Refund**](Refund.md)>


### Authorization

[RequestSignature](../README.md#RequestSignature), [ProjectIdentity](../README.md#ProjectIdentity)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Ранее созданный возврат с теми же параметрами. |  * Location -  <br>  * X-Request-Id -  <br>  |
| **202** | Возврат принят в обработку. |  * Location -  <br>  * X-Request-Id -  <br>  |
| **400** | Некорректные параметры запроса. |  * X-Request-Id -  <br>  |
| **401** | Не пройдена аутентификация или проверка подписи. |  * X-Request-Id -  <br>  |
| **404** | Ресурс не найден. |  * X-Request-Id -  <br>  |
| **409** | Параметры ранее созданного возврата отличаются. |  * X-Request-Id -  <br>  |
| **415** | Тело запроса должно быть JSON. |  * X-Request-Id -  <br>  |
| **422** | Операция невозможна в текущем статусе платежа. |  * X-Request-Id -  <br>  |
| **429** | Превышен лимит запросов. |  * X-Request-Id -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset - Unix-время сброса лимита. <br>  * Retry-After -  <br>  |
| **500** | Внутренняя ошибка сервиса. |  * X-Request-Id -  <br>  |
| **502** | Внешний сервис вернул некорректный ответ. |  * X-Request-Id -  <br>  |
| **503** | Сервис временно недоступен. |  * X-Request-Id -  <br>  |
| **504** | Внешний сервис не ответил вовремя. |  * X-Request-Id -  <br>  |


## getPaymentRefund

> Refund getPaymentRefund(paymentId)

Получить возврат

### Example

```java
// Import classes:
import io.opayments.sdk.ApiClient;
import io.opayments.sdk.ApiException;
import io.opayments.sdk.Configuration;
import io.opayments.sdk.auth.*;
import io.opayments.sdk.models.*;
import io.opayments.sdk.api.RefundsApi;

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

        RefundsApi apiInstance = new RefundsApi(defaultClient);
        UUID paymentId = UUID.fromString("c9ee7c85-4cc0-494f-a0de-0af7257a66a6"); // UUID | 
        try {
            Refund result = apiInstance.getPaymentRefund(paymentId);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling RefundsApi#getPaymentRefund");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Reason: " + e.getResponseBody());
            System.err.println("Response headers: " + e.getResponseHeaders());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **paymentId** | **UUID**|  | |

### Return type

[**Refund**](Refund.md)


### Authorization

[RequestSignature](../README.md#RequestSignature), [ProjectIdentity](../README.md#ProjectIdentity)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Возврат. |  * X-Request-Id -  <br>  |
| **400** | Некорректные параметры запроса. |  * X-Request-Id -  <br>  |
| **401** | Не пройдена аутентификация или проверка подписи. |  * X-Request-Id -  <br>  |
| **404** | Возврат не найден. |  * X-Request-Id -  <br>  |
| **429** | Превышен лимит запросов. |  * X-Request-Id -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset - Unix-время сброса лимита. <br>  * Retry-After -  <br>  |

## getPaymentRefundWithHttpInfo

> ApiResponse<Refund> getPaymentRefundWithHttpInfo(paymentId)

Получить возврат

### Example

```java
// Import classes:
import io.opayments.sdk.ApiClient;
import io.opayments.sdk.ApiException;
import io.opayments.sdk.ApiResponse;
import io.opayments.sdk.Configuration;
import io.opayments.sdk.auth.*;
import io.opayments.sdk.models.*;
import io.opayments.sdk.api.RefundsApi;

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

        RefundsApi apiInstance = new RefundsApi(defaultClient);
        UUID paymentId = UUID.fromString("c9ee7c85-4cc0-494f-a0de-0af7257a66a6"); // UUID | 
        try {
            ApiResponse<Refund> response = apiInstance.getPaymentRefundWithHttpInfo(paymentId);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling RefundsApi#getPaymentRefund");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Response headers: " + e.getResponseHeaders());
            System.err.println("Reason: " + e.getResponseBody());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **paymentId** | **UUID**|  | |

### Return type

ApiResponse<[**Refund**](Refund.md)>


### Authorization

[RequestSignature](../README.md#RequestSignature), [ProjectIdentity](../README.md#ProjectIdentity)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Возврат. |  * X-Request-Id -  <br>  |
| **400** | Некорректные параметры запроса. |  * X-Request-Id -  <br>  |
| **401** | Не пройдена аутентификация или проверка подписи. |  * X-Request-Id -  <br>  |
| **404** | Возврат не найден. |  * X-Request-Id -  <br>  |
| **429** | Превышен лимит запросов. |  * X-Request-Id -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset - Unix-время сброса лимита. <br>  * Retry-After -  <br>  |

