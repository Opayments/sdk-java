

# FinalRefund


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**paymentId** | **UUID** |  |  |
|**amount** | **Integer** | Сумма в копейках. |  |
|**currency** | [**CurrencyEnum**](#CurrencyEnum) |  |  |
|**status** | [**StatusEnum**](#StatusEnum) |  |  |
|**reason** | **String** |  |  [optional] |
|**failureCode** | **String** |  |  [optional] |
|**failureMessage** | **String** |  |  [optional] |
|**acceptedAt** | **OffsetDateTime** |  |  [optional] |
|**declinedAt** | **OffsetDateTime** |  |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  |
|**updatedAt** | **OffsetDateTime** |  |  |



## Enum: CurrencyEnum

| Name | Value |
|---- | -----|
| RUB | &quot;RUB&quot; |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| ACCEPTED | &quot;accepted&quot; |
| DECLINED | &quot;declined&quot; |



