

# PrepaymentPayment


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**paymentId** | **UUID** |  |  |
|**orderId** | **String** |  |  |
|**amount** | **Integer** | Сумма в копейках. |  |
|**currency** | [**CurrencyEnum**](#CurrencyEnum) |  |  |
|**description** | **String** |  |  [optional] |
|**paymentMethod** | [**PaymentMethodEnum**](#PaymentMethodEnum) |  |  |
|**status** | [**StatusEnum**](#StatusEnum) |  |  |
|**paymentUrl** | **URI** | Адрес оплаты для платежа в статусе pending. |  [optional] |
|**expiresAt** | **OffsetDateTime** |  |  [optional] |
|**failureCode** | **String** |  |  [optional] |
|**failureMessage** | **String** |  |  [optional] |
|**completedAt** | **OffsetDateTime** |  |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  |
|**updatedAt** | **OffsetDateTime** |  |  |



## Enum: CurrencyEnum

| Name | Value |
|---- | -----|
| RUB | &quot;RUB&quot; |



## Enum: PaymentMethodEnum

| Name | Value |
|---- | -----|
| SBP | &quot;sbp&quot; |
| TPAY | &quot;tpay&quot; |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| PENDING | &quot;pending&quot; |



