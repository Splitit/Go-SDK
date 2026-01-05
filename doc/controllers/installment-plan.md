# Installment Plan

```go
installmentPlanController := client.InstallmentPlanController()
```

## Class Name

`InstallmentPlanController`

## Methods

* [Installment Plan Get](../../doc/controllers/installment-plan.md#installment-plan-get)
* [Installment Plan Search](../../doc/controllers/installment-plan.md#installment-plan-search)
* [Installment Plan Post](../../doc/controllers/installment-plan.md#installment-plan-post)
* [Installment Plan Post 2](../../doc/controllers/installment-plan.md#installment-plan-post-2)
* [Installment Plan Verify Authorization](../../doc/controllers/installment-plan.md#installment-plan-verify-authorization)
* [Installment Plan Update Order](../../doc/controllers/installment-plan.md#installment-plan-update-order)
* [Installment Plan Update Order 2](../../doc/controllers/installment-plan.md#installment-plan-update-order-2)
* [Installment Plan Refund](../../doc/controllers/installment-plan.md#installment-plan-refund)
* [Installment Plan Check Eligibility](../../doc/controllers/installment-plan.md#installment-plan-check-eligibility)
* [Installment Plan Get Eligibility Terms and Condition](../../doc/controllers/installment-plan.md#installment-plan-get-eligibility-terms-and-condition)


# Installment Plan Get

```go
InstallmentPlanGet(
    ctx context.Context,
    installmentPlanNumber string,
    xSplititTouchPoint models.Optional[string]) (
    models.ApiResponse[models.InstallmentPlanGetResponse],
    error)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `installmentPlanNumber` | `string` | Template, Required | - |
| `xSplititTouchPoint` | `models.Optional[string]` | Header, Optional | TouchPoint |

## Requires scope

### OAuth2-sandbox

`api.v3`

### OAuth2-production

`api.v3`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [models.InstallmentPlanGetResponse](../../doc/models/installment-plan-get-response.md).

## Example Usage

```go
ctx := context.Background()

installmentPlanNumber := "installmentPlanNumber6"

apiResponse, err := installmentPlanController.InstallmentPlanGet(ctx, installmentPlanNumber, models.EmptyOptional[string]())
if err != nil {
    log.Fatalln(err)
} else {
    // Printing the result and response
    fmt.Println(apiResponse.Data)
    fmt.Println(apiResponse.Response.StatusCode)
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 403 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 404 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 500 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |


# Installment Plan Search

```go
InstallmentPlanSearch(
    ctx context.Context,
    installmentPlanNumber models.Optional[string],
    refOrderNumber models.Optional[string],
    extendedParams models.Optional[interface{}],
    xSplititTouchPoint models.Optional[string]) (
    models.ApiResponse[models.InstallmentPlanSearchResponse],
    error)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `installmentPlanNumber` | `models.Optional[string]` | Query, Optional | - |
| `refOrderNumber` | `models.Optional[string]` | Query, Optional | - |
| `extendedParams` | `models.Optional[interface{}]` | Query, Optional | - |
| `xSplititTouchPoint` | `models.Optional[string]` | Header, Optional | TouchPoint |

## Requires scope

### OAuth2-sandbox

`api.v3`

### OAuth2-production

`api.v3`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [models.InstallmentPlanSearchResponse](../../doc/models/installment-plan-search-response.md).

## Example Usage

```go
ctx := context.Background()

apiResponse, err := installmentPlanController.InstallmentPlanSearch(ctx, models.EmptyOptional[string](), models.EmptyOptional[string](), models.EmptyOptional[interface{}](), models.EmptyOptional[string]())
if err != nil {
    log.Fatalln(err)
} else {
    // Printing the result and response
    fmt.Println(apiResponse.Data)
    fmt.Println(apiResponse.Response.StatusCode)
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 403 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 404 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 500 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |


# Installment Plan Post

```go
InstallmentPlanPost(
    ctx context.Context,
    xSplititIdempotencyKey string,
    body models.InstallmentPlanInitiateRequest,
    xSplititTestMode models.Optional[models.TestModesEnum],
    xSplititTouchPoint models.Optional[string]) (
    models.ApiResponse[models.InitiatePlanResponse],
    error)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `xSplititIdempotencyKey` | `string` | Header, Required | - |
| `body` | [`models.InstallmentPlanInitiateRequest`](../../doc/models/installment-plan-initiate-request.md) | Body, Required | - |
| `xSplititTestMode` | [`models.Optional[models.TestModesEnum]`](../../doc/models/test-modes-enum.md) | Header, Optional | - |
| `xSplititTouchPoint` | `models.Optional[string]` | Header, Optional | TouchPoint |

## Requires scope

### OAuth2-sandbox

`api.v3`

### OAuth2-production

`api.v3`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [models.InitiatePlanResponse](../../doc/models/initiate-plan-response.md).

## Example Usage

```go
ctx := context.Background()

xSplititIdempotencyKey := "X-Splitit-IdempotencyKey2"

body := models.InstallmentPlanInitiateRequest{
}

apiResponse, err := installmentPlanController.InstallmentPlanPost(ctx, xSplititIdempotencyKey, body, models.EmptyOptional[models.TestModesEnum](), models.EmptyOptional[string]())
if err != nil {
    log.Fatalln(err)
} else {
    // Printing the result and response
    fmt.Println(apiResponse.Data)
    fmt.Println(apiResponse.Response.StatusCode)
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | - | [`PlanErrorResponseException`](../../doc/models/plan-error-response-exception.md) |
| 401 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 403 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 404 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 500 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |


# Installment Plan Post 2

```go
InstallmentPlanPost2(
    ctx context.Context,
    xSplititIdempotencyKey string,
    body models.InstallmentPlanCreateRequest,
    xSplititTestMode models.Optional[models.TestModesEnum],
    xSplititTouchPoint models.Optional[string]) (
    models.ApiResponse[models.InstallmentPlanCreateResponse],
    error)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `xSplititIdempotencyKey` | `string` | Header, Required | - |
| `body` | [`models.InstallmentPlanCreateRequest`](../../doc/models/installment-plan-create-request.md) | Body, Required | - |
| `xSplititTestMode` | [`models.Optional[models.TestModesEnum]`](../../doc/models/test-modes-enum.md) | Header, Optional | - |
| `xSplititTouchPoint` | `models.Optional[string]` | Header, Optional | TouchPoint |

## Requires scope

### OAuth2-sandbox

`api.v3`

### OAuth2-production

`api.v3`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [models.InstallmentPlanCreateResponse](../../doc/models/installment-plan-create-response.md).

## Example Usage

```go
ctx := context.Background()

xSplititIdempotencyKey := "X-Splitit-IdempotencyKey2"

body := models.InstallmentPlanCreateRequest{
    AutoCapture:                false,
    TermsAndConditionsAccepted: false,
}

apiResponse, err := installmentPlanController.InstallmentPlanPost2(ctx, xSplititIdempotencyKey, body, models.EmptyOptional[models.TestModesEnum](), models.EmptyOptional[string]())
if err != nil {
    log.Fatalln(err)
} else {
    // Printing the result and response
    fmt.Println(apiResponse.Data)
    fmt.Println(apiResponse.Response.StatusCode)
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | - | [`PlanErrorResponseException`](../../doc/models/plan-error-response-exception.md) |
| 401 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 403 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 404 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 500 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |


# Installment Plan Verify Authorization

```go
InstallmentPlanVerifyAuthorization(
    ctx context.Context,
    installmentPlanNumber string,
    xSplititTouchPoint models.Optional[string]) (
    models.ApiResponse[models.VerifyAuthorizationResponse],
    error)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `installmentPlanNumber` | `string` | Template, Required | - |
| `xSplititTouchPoint` | `models.Optional[string]` | Header, Optional | TouchPoint |

## Requires scope

### OAuth2-sandbox

`api.v3`

### OAuth2-production

`api.v3`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [models.VerifyAuthorizationResponse](../../doc/models/verify-authorization-response.md).

## Example Usage

```go
ctx := context.Background()

installmentPlanNumber := "installmentPlanNumber6"

apiResponse, err := installmentPlanController.InstallmentPlanVerifyAuthorization(ctx, installmentPlanNumber, models.EmptyOptional[string]())
if err != nil {
    log.Fatalln(err)
} else {
    // Printing the result and response
    fmt.Println(apiResponse.Data)
    fmt.Println(apiResponse.Response.StatusCode)
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 403 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 404 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 500 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |


# Installment Plan Update Order

```go
InstallmentPlanUpdateOrder(
    ctx context.Context,
    installmentPlanNumber string,
    xSplititIdempotencyKey string,
    body models.InstallmentPlanUpdateRequest,
    xSplititTouchPoint models.Optional[string]) (
    models.ApiResponse[models.InstallmentPlanUpdateResponse],
    error)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `installmentPlanNumber` | `string` | Template, Required | - |
| `xSplititIdempotencyKey` | `string` | Header, Required | - |
| `body` | [`models.InstallmentPlanUpdateRequest`](../../doc/models/installment-plan-update-request.md) | Body, Required | - |
| `xSplititTouchPoint` | `models.Optional[string]` | Header, Optional | TouchPoint |

## Requires scope

### OAuth2-sandbox

`api.v3`

### OAuth2-production

`api.v3`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [models.InstallmentPlanUpdateResponse](../../doc/models/installment-plan-update-response.md).

## Example Usage

```go
ctx := context.Background()

installmentPlanNumber := "installmentPlanNumber6"

xSplititIdempotencyKey := "X-Splitit-IdempotencyKey2"

body := models.InstallmentPlanUpdateRequest{
}

apiResponse, err := installmentPlanController.InstallmentPlanUpdateOrder(ctx, installmentPlanNumber, xSplititIdempotencyKey, body, models.EmptyOptional[string]())
if err != nil {
    log.Fatalln(err)
} else {
    // Printing the result and response
    fmt.Println(apiResponse.Data)
    fmt.Println(apiResponse.Response.StatusCode)
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 403 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 404 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 500 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |


# Installment Plan Update Order 2

```go
InstallmentPlanUpdateOrder2(
    ctx context.Context,
    xSplititIdempotencyKey string,
    body models.InstallmentPlanUpdateRequestByIdentifier,
    xSplititTouchPoint models.Optional[string]) (
    models.ApiResponse[models.InstallmentPlanUpdateResponse],
    error)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `xSplititIdempotencyKey` | `string` | Header, Required | - |
| `body` | [`models.InstallmentPlanUpdateRequestByIdentifier`](../../doc/models/installment-plan-update-request-by-identifier.md) | Body, Required | - |
| `xSplititTouchPoint` | `models.Optional[string]` | Header, Optional | TouchPoint |

## Requires scope

### OAuth2-sandbox

`api.v3`

### OAuth2-production

`api.v3`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [models.InstallmentPlanUpdateResponse](../../doc/models/installment-plan-update-response.md).

## Example Usage

```go
ctx := context.Background()

xSplititIdempotencyKey := "X-Splitit-IdempotencyKey2"

body := models.InstallmentPlanUpdateRequestByIdentifier{
}

apiResponse, err := installmentPlanController.InstallmentPlanUpdateOrder2(ctx, xSplititIdempotencyKey, body, models.EmptyOptional[string]())
if err != nil {
    log.Fatalln(err)
} else {
    // Printing the result and response
    fmt.Println(apiResponse.Data)
    fmt.Println(apiResponse.Response.StatusCode)
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 403 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 404 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 500 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |


# Installment Plan Refund

```go
InstallmentPlanRefund(
    ctx context.Context,
    installmentPlanNumber string,
    xSplititIdempotencyKey string,
    body models.InstallmentPlanRefundRequest,
    xSplititTouchPoint models.Optional[string]) (
    models.ApiResponse[models.InstallmentPlanRefundResponse],
    error)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `installmentPlanNumber` | `string` | Template, Required | - |
| `xSplititIdempotencyKey` | `string` | Header, Required | - |
| `body` | [`models.InstallmentPlanRefundRequest`](../../doc/models/installment-plan-refund-request.md) | Body, Required | - |
| `xSplititTouchPoint` | `models.Optional[string]` | Header, Optional | TouchPoint |

## Requires scope

### OAuth2-sandbox

`api.v3`

### OAuth2-production

`api.v3`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [models.InstallmentPlanRefundResponse](../../doc/models/installment-plan-refund-response.md).

## Example Usage

```go
ctx := context.Background()

installmentPlanNumber := "installmentPlanNumber6"

xSplititIdempotencyKey := "X-Splitit-IdempotencyKey2"

body := models.InstallmentPlanRefundRequest{
    Amount:               "Amount8",
}

apiResponse, err := installmentPlanController.InstallmentPlanRefund(ctx, installmentPlanNumber, xSplititIdempotencyKey, body, models.EmptyOptional[string]())
if err != nil {
    log.Fatalln(err)
} else {
    // Printing the result and response
    fmt.Println(apiResponse.Data)
    fmt.Println(apiResponse.Response.StatusCode)
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 403 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 404 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 500 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |


# Installment Plan Check Eligibility

```go
InstallmentPlanCheckEligibility(
    ctx context.Context,
    xSplititIdempotencyKey string,
    body models.CheckInstallmentsEligibilityRequest,
    xSplititTouchPoint models.Optional[string]) (
    models.ApiResponse[models.InstallmentsEligibilityResponse],
    error)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `xSplititIdempotencyKey` | `string` | Header, Required | - |
| `body` | [`models.CheckInstallmentsEligibilityRequest`](../../doc/models/check-installments-eligibility-request.md) | Body, Required | - |
| `xSplititTouchPoint` | `models.Optional[string]` | Header, Optional | TouchPoint |

## Requires scope

### OAuth2-sandbox

`api.v3`

### OAuth2-production

`api.v3`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [models.InstallmentsEligibilityResponse](../../doc/models/installments-eligibility-response.md).

## Example Usage

```go
ctx := context.Background()

xSplititIdempotencyKey := "X-Splitit-IdempotencyKey2"

body := models.CheckInstallmentsEligibilityRequest{
}

apiResponse, err := installmentPlanController.InstallmentPlanCheckEligibility(ctx, xSplititIdempotencyKey, body, models.EmptyOptional[string]())
if err != nil {
    log.Fatalln(err)
} else {
    // Printing the result and response
    fmt.Println(apiResponse.Data)
    fmt.Println(apiResponse.Response.StatusCode)
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 403 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 404 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 500 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |


# Installment Plan Get Eligibility Terms and Condition

```go
InstallmentPlanGetEligibilityTermsAndCondition(
    ctx context.Context,
    ipn string,
    xSplititTouchPoint models.Optional[string]) (
    models.ApiResponse[models.EligibilityTermsAndConditionResponse],
    error)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ipn` | `string` | Template, Required | - |
| `xSplititTouchPoint` | `models.Optional[string]` | Header, Optional | TouchPoint |

## Requires scope

### OAuth2-sandbox

`api.v3`

### OAuth2-production

`api.v3`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [models.EligibilityTermsAndConditionResponse](../../doc/models/eligibility-terms-and-condition-response.md).

## Example Usage

```go
ctx := context.Background()

ipn := "ipn4"

apiResponse, err := installmentPlanController.InstallmentPlanGetEligibilityTermsAndCondition(ctx, ipn, models.EmptyOptional[string]())
if err != nil {
    log.Fatalln(err)
} else {
    // Printing the result and response
    fmt.Println(apiResponse.Data)
    fmt.Println(apiResponse.Response.StatusCode)
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 403 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 404 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 500 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |

