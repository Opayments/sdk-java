

# CreateTpayPaymentRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**orderId** | **String** | Идентификатор заказа в системе мерчанта. |  |
|**amount** | **Integer** | Сумма в копейках. |  |
|**currency** | [**CurrencyEnum**](#CurrencyEnum) |  |  |
|**description** | **String** |  |  [optional] |
|**ip** | **String** | IP-адрес плательщика: IPv4 или IPv6. |  |
|**callbackUrl** | **URI** | HTTPS-адрес уведомлений. |  |
|**successUrl** | **URI** | HTTPS-адрес для успешной оплаты. |  |
|**failedUrl** | **URI** | HTTPS-адрес для отменённой оплаты. |  |
|**deviceData** | [**TpayDeviceData**](TpayDeviceData.md) |  |  |



## Enum: CurrencyEnum

| Name | Value |
|---- | -----|
| RUB | &quot;RUB&quot; |



