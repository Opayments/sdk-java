# PaymentsApi

All URIs are relative to *https://api.opayments.io/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getPayment**](PaymentsApi.md#getPayment) | **GET** /payments/{paymentId} | Получить платёж |
| [**getPaymentWithHttpInfo**](PaymentsApi.md#getPaymentWithHttpInfo) | **GET** /payments/{paymentId} | Получить платёж |
| [**listPayments**](PaymentsApi.md#listPayments) | **GET** /payments | Найти платежи |
| [**listPaymentsWithHttpInfo**](PaymentsApi.md#listPaymentsWithHttpInfo) | **GET** /payments | Найти платежи |



## getPayment

> PaymentDetails getPayment(paymentId)

Получить платёж

### Example

```java
// Import classes:
import io.opayments.sdk.ApiClient;
import io.opayments.sdk.ApiException;
import io.opayments.sdk.Configuration;
import io.opayments.sdk.auth.*;
import io.opayments.sdk.models.*;
import io.opayments.sdk.api.PaymentsApi;

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

        PaymentsApi apiInstance = new PaymentsApi(defaultClient);
        UUID paymentId = UUID.fromString("c9ee7c85-4cc0-494f-a0de-0af7257a66a6"); // UUID | 
        try {
            PaymentDetails result = apiInstance.getPayment(paymentId);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling PaymentsApi#getPayment");
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

[**PaymentDetails**](PaymentDetails.md)


### Authorization

[RequestSignature](../README.md#RequestSignature), [ProjectIdentity](../README.md#ProjectIdentity)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Платёж. |  * X-Request-Id -  <br>  |
| **400** | Некорректные параметры запроса. |  * X-Request-Id -  <br>  |
| **401** | Не пройдена аутентификация или проверка подписи. |  * X-Request-Id -  <br>  |
| **404** | Ресурс не найден. |  * X-Request-Id -  <br>  |
| **429** | Превышен лимит запросов. |  * X-Request-Id -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset - Unix-время сброса лимита. <br>  * Retry-After -  <br>  |

## getPaymentWithHttpInfo

> ApiResponse<PaymentDetails> getPaymentWithHttpInfo(paymentId)

Получить платёж

### Example

```java
// Import classes:
import io.opayments.sdk.ApiClient;
import io.opayments.sdk.ApiException;
import io.opayments.sdk.ApiResponse;
import io.opayments.sdk.Configuration;
import io.opayments.sdk.auth.*;
import io.opayments.sdk.models.*;
import io.opayments.sdk.api.PaymentsApi;

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

        PaymentsApi apiInstance = new PaymentsApi(defaultClient);
        UUID paymentId = UUID.fromString("c9ee7c85-4cc0-494f-a0de-0af7257a66a6"); // UUID | 
        try {
            ApiResponse<PaymentDetails> response = apiInstance.getPaymentWithHttpInfo(paymentId);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling PaymentsApi#getPayment");
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

ApiResponse<[**PaymentDetails**](PaymentDetails.md)>


### Authorization

[RequestSignature](../README.md#RequestSignature), [ProjectIdentity](../README.md#ProjectIdentity)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Платёж. |  * X-Request-Id -  <br>  |
| **400** | Некорректные параметры запроса. |  * X-Request-Id -  <br>  |
| **401** | Не пройдена аутентификация или проверка подписи. |  * X-Request-Id -  <br>  |
| **404** | Ресурс не найден. |  * X-Request-Id -  <br>  |
| **429** | Превышен лимит запросов. |  * X-Request-Id -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset - Unix-время сброса лимита. <br>  * Retry-After -  <br>  |


## listPayments

> PaymentList listPayments(orderId, status, paymentMethod, amountFrom, amountTo, createdFrom, createdTo, sort, sortDirection, cursor, limit)

Найти платежи

Возвращает список платежей проекта.

### Example

```java
// Import classes:
import io.opayments.sdk.ApiClient;
import io.opayments.sdk.ApiException;
import io.opayments.sdk.Configuration;
import io.opayments.sdk.auth.*;
import io.opayments.sdk.models.*;
import io.opayments.sdk.api.PaymentsApi;

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

        PaymentsApi apiInstance = new PaymentsApi(defaultClient);
        String orderId = "orderId_example"; // String | Идентификатор заказа в системе мерчанта.
        List<String> status = Arrays.asList(); // List<String> | 
        String paymentMethod = "sbp"; // String | 
        Integer amountFrom = 56; // Integer | Не больше amountTo, если он передан.
        Integer amountTo = 56; // Integer | Не меньше amountFrom, если он передан.
        OffsetDateTime createdFrom = OffsetDateTime.now(); // OffsetDateTime | Не позже createdTo, если он передан.
        OffsetDateTime createdTo = OffsetDateTime.now(); // OffsetDateTime | Не раньше createdFrom, если он передан.
        String sort = "createdAt"; // String | 
        String sortDirection = "asc"; // String | 
        String cursor = "cursor_example"; // String | Непрозрачный курсор из предыдущего ответа. Используйте только с теми же фильтрами и сортировкой.
        Integer limit = 20; // Integer | Количество записей в ответе.
        try {
            PaymentList result = apiInstance.listPayments(orderId, status, paymentMethod, amountFrom, amountTo, createdFrom, createdTo, sort, sortDirection, cursor, limit);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling PaymentsApi#listPayments");
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
| **orderId** | **String**| Идентификатор заказа в системе мерчанта. | [optional] |
| **status** | [**List&lt;String&gt;**](String.md)|  | [optional] [enum: pending, succeeded, cancelled, chargebacked, refunded] |
| **paymentMethod** | **String**|  | [optional] [enum: sbp, tpay] |
| **amountFrom** | **Integer**| Не больше amountTo, если он передан. | [optional] |
| **amountTo** | **Integer**| Не меньше amountFrom, если он передан. | [optional] |
| **createdFrom** | **OffsetDateTime**| Не позже createdTo, если он передан. | [optional] |
| **createdTo** | **OffsetDateTime**| Не раньше createdFrom, если он передан. | [optional] |
| **sort** | **String**|  | [optional] [default to createdAt] [enum: createdAt, amount] |
| **sortDirection** | **String**|  | [optional] [default to desc] [enum: asc, desc] |
| **cursor** | **String**| Непрозрачный курсор из предыдущего ответа. Используйте только с теми же фильтрами и сортировкой. | [optional] |
| **limit** | **Integer**| Количество записей в ответе. | [optional] [default to 20] |

### Return type

[**PaymentList**](PaymentList.md)


### Authorization

[RequestSignature](../README.md#RequestSignature), [ProjectIdentity](../README.md#ProjectIdentity)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Страница платежей. |  * X-Request-Id -  <br>  |
| **400** | Некорректные параметры запроса. |  * X-Request-Id -  <br>  |
| **401** | Не пройдена аутентификация или проверка подписи. |  * X-Request-Id -  <br>  |
| **403** | Операция недоступна для проекта. |  * X-Request-Id -  <br>  |
| **429** | Превышен лимит запросов. |  * X-Request-Id -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset - Unix-время сброса лимита. <br>  * Retry-After -  <br>  |

## listPaymentsWithHttpInfo

> ApiResponse<PaymentList> listPaymentsWithHttpInfo(orderId, status, paymentMethod, amountFrom, amountTo, createdFrom, createdTo, sort, sortDirection, cursor, limit)

Найти платежи

Возвращает список платежей проекта.

### Example

```java
// Import classes:
import io.opayments.sdk.ApiClient;
import io.opayments.sdk.ApiException;
import io.opayments.sdk.ApiResponse;
import io.opayments.sdk.Configuration;
import io.opayments.sdk.auth.*;
import io.opayments.sdk.models.*;
import io.opayments.sdk.api.PaymentsApi;

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

        PaymentsApi apiInstance = new PaymentsApi(defaultClient);
        String orderId = "orderId_example"; // String | Идентификатор заказа в системе мерчанта.
        List<String> status = Arrays.asList(); // List<String> | 
        String paymentMethod = "sbp"; // String | 
        Integer amountFrom = 56; // Integer | Не больше amountTo, если он передан.
        Integer amountTo = 56; // Integer | Не меньше amountFrom, если он передан.
        OffsetDateTime createdFrom = OffsetDateTime.now(); // OffsetDateTime | Не позже createdTo, если он передан.
        OffsetDateTime createdTo = OffsetDateTime.now(); // OffsetDateTime | Не раньше createdFrom, если он передан.
        String sort = "createdAt"; // String | 
        String sortDirection = "asc"; // String | 
        String cursor = "cursor_example"; // String | Непрозрачный курсор из предыдущего ответа. Используйте только с теми же фильтрами и сортировкой.
        Integer limit = 20; // Integer | Количество записей в ответе.
        try {
            ApiResponse<PaymentList> response = apiInstance.listPaymentsWithHttpInfo(orderId, status, paymentMethod, amountFrom, amountTo, createdFrom, createdTo, sort, sortDirection, cursor, limit);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling PaymentsApi#listPayments");
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
| **orderId** | **String**| Идентификатор заказа в системе мерчанта. | [optional] |
| **status** | [**List&lt;String&gt;**](String.md)|  | [optional] [enum: pending, succeeded, cancelled, chargebacked, refunded] |
| **paymentMethod** | **String**|  | [optional] [enum: sbp, tpay] |
| **amountFrom** | **Integer**| Не больше amountTo, если он передан. | [optional] |
| **amountTo** | **Integer**| Не меньше amountFrom, если он передан. | [optional] |
| **createdFrom** | **OffsetDateTime**| Не позже createdTo, если он передан. | [optional] |
| **createdTo** | **OffsetDateTime**| Не раньше createdFrom, если он передан. | [optional] |
| **sort** | **String**|  | [optional] [default to createdAt] [enum: createdAt, amount] |
| **sortDirection** | **String**|  | [optional] [default to desc] [enum: asc, desc] |
| **cursor** | **String**| Непрозрачный курсор из предыдущего ответа. Используйте только с теми же фильтрами и сортировкой. | [optional] |
| **limit** | **Integer**| Количество записей в ответе. | [optional] [default to 20] |

### Return type

ApiResponse<[**PaymentList**](PaymentList.md)>


### Authorization

[RequestSignature](../README.md#RequestSignature), [ProjectIdentity](../README.md#ProjectIdentity)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Страница платежей. |  * X-Request-Id -  <br>  |
| **400** | Некорректные параметры запроса. |  * X-Request-Id -  <br>  |
| **401** | Не пройдена аутентификация или проверка подписи. |  * X-Request-Id -  <br>  |
| **403** | Операция недоступна для проекта. |  * X-Request-Id -  <br>  |
| **429** | Превышен лимит запросов. |  * X-Request-Id -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset - Unix-время сброса лимита. <br>  * Retry-After -  <br>  |

