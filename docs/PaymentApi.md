# PaymentApi

All URIs are relative to *https://api.opayments.io/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createSbpPayment**](PaymentApi.md#createSbpPayment) | **POST** /payments/sbp | Создать платёж по СБП |
| [**createSbpPaymentWithHttpInfo**](PaymentApi.md#createSbpPaymentWithHttpInfo) | **POST** /payments/sbp | Создать платёж по СБП |
| [**createTpayPayment**](PaymentApi.md#createTpayPayment) | **POST** /payments/tpay | Создать платёж через T-Pay |
| [**createTpayPaymentWithHttpInfo**](PaymentApi.md#createTpayPaymentWithHttpInfo) | **POST** /payments/tpay | Создать платёж через T-Pay |



## createSbpPayment

> Payment createSbpPayment(createSbpPaymentRequest)

Создать платёж по СБП

### Example

```java
// Import classes:
import io.opayments.sdk.ApiClient;
import io.opayments.sdk.ApiException;
import io.opayments.sdk.Configuration;
import io.opayments.sdk.auth.*;
import io.opayments.sdk.models.*;
import io.opayments.sdk.api.PaymentApi;

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

        PaymentApi apiInstance = new PaymentApi(defaultClient);
        CreateSbpPaymentRequest createSbpPaymentRequest = new CreateSbpPaymentRequest(); // CreateSbpPaymentRequest | 
        try {
            Payment result = apiInstance.createSbpPayment(createSbpPaymentRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling PaymentApi#createSbpPayment");
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
| **createSbpPaymentRequest** | [**CreateSbpPaymentRequest**](CreateSbpPaymentRequest.md)|  | |

### Return type

[**Payment**](Payment.md)


### Authorization

[RequestSignature](../README.md#RequestSignature), [ProjectIdentity](../README.md#ProjectIdentity)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Ранее созданный платёж СБП. |  * Location -  <br>  * X-Request-Id -  <br>  |
| **201** | Платёж через СБП создан. |  * Location -  <br>  * X-Request-Id -  <br>  |
| **400** | Некорректные параметры запроса. |  * X-Request-Id -  <br>  |
| **401** | Не пройдена аутентификация или проверка подписи. |  * X-Request-Id -  <br>  |
| **403** | Операция недоступна для проекта. |  * X-Request-Id -  <br>  |
| **409** | Запрос конфликтует с текущим состоянием ресурса. |  * X-Request-Id -  <br>  |
| **415** | Тело запроса должно быть JSON. |  * X-Request-Id -  <br>  |
| **429** | Превышен лимит запросов. |  * X-Request-Id -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset - Unix-время сброса лимита. <br>  * Retry-After -  <br>  |
| **502** | Внешний сервис вернул некорректный ответ. |  * X-Request-Id -  <br>  |
| **503** | Сервис временно недоступен. |  * X-Request-Id -  <br>  |
| **504** | Внешний сервис не ответил вовремя. |  * X-Request-Id -  <br>  |

## createSbpPaymentWithHttpInfo

> ApiResponse<Payment> createSbpPaymentWithHttpInfo(createSbpPaymentRequest)

Создать платёж по СБП

### Example

```java
// Import classes:
import io.opayments.sdk.ApiClient;
import io.opayments.sdk.ApiException;
import io.opayments.sdk.ApiResponse;
import io.opayments.sdk.Configuration;
import io.opayments.sdk.auth.*;
import io.opayments.sdk.models.*;
import io.opayments.sdk.api.PaymentApi;

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

        PaymentApi apiInstance = new PaymentApi(defaultClient);
        CreateSbpPaymentRequest createSbpPaymentRequest = new CreateSbpPaymentRequest(); // CreateSbpPaymentRequest | 
        try {
            ApiResponse<Payment> response = apiInstance.createSbpPaymentWithHttpInfo(createSbpPaymentRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling PaymentApi#createSbpPayment");
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
| **createSbpPaymentRequest** | [**CreateSbpPaymentRequest**](CreateSbpPaymentRequest.md)|  | |

### Return type

ApiResponse<[**Payment**](Payment.md)>


### Authorization

[RequestSignature](../README.md#RequestSignature), [ProjectIdentity](../README.md#ProjectIdentity)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Ранее созданный платёж СБП. |  * Location -  <br>  * X-Request-Id -  <br>  |
| **201** | Платёж через СБП создан. |  * Location -  <br>  * X-Request-Id -  <br>  |
| **400** | Некорректные параметры запроса. |  * X-Request-Id -  <br>  |
| **401** | Не пройдена аутентификация или проверка подписи. |  * X-Request-Id -  <br>  |
| **403** | Операция недоступна для проекта. |  * X-Request-Id -  <br>  |
| **409** | Запрос конфликтует с текущим состоянием ресурса. |  * X-Request-Id -  <br>  |
| **415** | Тело запроса должно быть JSON. |  * X-Request-Id -  <br>  |
| **429** | Превышен лимит запросов. |  * X-Request-Id -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset - Unix-время сброса лимита. <br>  * Retry-After -  <br>  |
| **502** | Внешний сервис вернул некорректный ответ. |  * X-Request-Id -  <br>  |
| **503** | Сервис временно недоступен. |  * X-Request-Id -  <br>  |
| **504** | Внешний сервис не ответил вовремя. |  * X-Request-Id -  <br>  |


## createTpayPayment

> Payment createTpayPayment(createTpayPaymentRequest)

Создать платёж через T-Pay

### Example

```java
// Import classes:
import io.opayments.sdk.ApiClient;
import io.opayments.sdk.ApiException;
import io.opayments.sdk.Configuration;
import io.opayments.sdk.auth.*;
import io.opayments.sdk.models.*;
import io.opayments.sdk.api.PaymentApi;

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

        PaymentApi apiInstance = new PaymentApi(defaultClient);
        CreateTpayPaymentRequest createTpayPaymentRequest = new CreateTpayPaymentRequest(); // CreateTpayPaymentRequest | 
        try {
            Payment result = apiInstance.createTpayPayment(createTpayPaymentRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling PaymentApi#createTpayPayment");
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
| **createTpayPaymentRequest** | [**CreateTpayPaymentRequest**](CreateTpayPaymentRequest.md)|  | |

### Return type

[**Payment**](Payment.md)


### Authorization

[RequestSignature](../README.md#RequestSignature), [ProjectIdentity](../README.md#ProjectIdentity)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Ранее созданный платёж T-Pay. |  * Location -  <br>  * X-Request-Id -  <br>  |
| **201** | Платёж через T-Pay создан. |  * Location -  <br>  * X-Request-Id -  <br>  |
| **400** | Некорректные параметры запроса. |  * X-Request-Id -  <br>  |
| **401** | Не пройдена аутентификация или проверка подписи. |  * X-Request-Id -  <br>  |
| **403** | Операция недоступна для проекта. |  * X-Request-Id -  <br>  |
| **409** | Запрос конфликтует с текущим состоянием ресурса. |  * X-Request-Id -  <br>  |
| **415** | Тело запроса должно быть JSON. |  * X-Request-Id -  <br>  |
| **429** | Превышен лимит запросов. |  * X-Request-Id -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset - Unix-время сброса лимита. <br>  * Retry-After -  <br>  |
| **502** | Внешний сервис вернул некорректный ответ. |  * X-Request-Id -  <br>  |
| **503** | Сервис временно недоступен. |  * X-Request-Id -  <br>  |
| **504** | Внешний сервис не ответил вовремя. |  * X-Request-Id -  <br>  |

## createTpayPaymentWithHttpInfo

> ApiResponse<Payment> createTpayPaymentWithHttpInfo(createTpayPaymentRequest)

Создать платёж через T-Pay

### Example

```java
// Import classes:
import io.opayments.sdk.ApiClient;
import io.opayments.sdk.ApiException;
import io.opayments.sdk.ApiResponse;
import io.opayments.sdk.Configuration;
import io.opayments.sdk.auth.*;
import io.opayments.sdk.models.*;
import io.opayments.sdk.api.PaymentApi;

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

        PaymentApi apiInstance = new PaymentApi(defaultClient);
        CreateTpayPaymentRequest createTpayPaymentRequest = new CreateTpayPaymentRequest(); // CreateTpayPaymentRequest | 
        try {
            ApiResponse<Payment> response = apiInstance.createTpayPaymentWithHttpInfo(createTpayPaymentRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling PaymentApi#createTpayPayment");
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
| **createTpayPaymentRequest** | [**CreateTpayPaymentRequest**](CreateTpayPaymentRequest.md)|  | |

### Return type

ApiResponse<[**Payment**](Payment.md)>


### Authorization

[RequestSignature](../README.md#RequestSignature), [ProjectIdentity](../README.md#ProjectIdentity)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Ранее созданный платёж T-Pay. |  * Location -  <br>  * X-Request-Id -  <br>  |
| **201** | Платёж через T-Pay создан. |  * Location -  <br>  * X-Request-Id -  <br>  |
| **400** | Некорректные параметры запроса. |  * X-Request-Id -  <br>  |
| **401** | Не пройдена аутентификация или проверка подписи. |  * X-Request-Id -  <br>  |
| **403** | Операция недоступна для проекта. |  * X-Request-Id -  <br>  |
| **409** | Запрос конфликтует с текущим состоянием ресурса. |  * X-Request-Id -  <br>  |
| **415** | Тело запроса должно быть JSON. |  * X-Request-Id -  <br>  |
| **429** | Превышен лимит запросов. |  * X-Request-Id -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset - Unix-время сброса лимита. <br>  * Retry-After -  <br>  |
| **502** | Внешний сервис вернул некорректный ответ. |  * X-Request-Id -  <br>  |
| **503** | Сервис временно недоступен. |  * X-Request-Id -  <br>  |
| **504** | Внешний сервис не ответил вовремя. |  * X-Request-Id -  <br>  |

