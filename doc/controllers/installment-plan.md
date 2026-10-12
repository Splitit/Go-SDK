# Installment Plan

```go
installmentPlanController := client.InstallmentPlanController()
```

## Class Name

`InstallmentPlanController`

## Methods

* [Installment Plan Check Card Validity](../../doc/controllers/installment-plan.md#installment-plan-check-card-validity)
* [Installment Plan Create Offers](../../doc/controllers/installment-plan.md#installment-plan-create-offers)
* [Installment Plan Generate Payment Link](../../doc/controllers/installment-plan.md#installment-plan-generate-payment-link)
* [Installment Plan Update Offers](../../doc/controllers/installment-plan.md#installment-plan-update-offers)
* [Installment Plan Authorize](../../doc/controllers/installment-plan.md#installment-plan-authorize)
* [Installment Plan Update Order](../../doc/controllers/installment-plan.md#installment-plan-update-order)
* [Installment Plan Get by Installment Plan Number](../../doc/controllers/installment-plan.md#installment-plan-get-by-installment-plan-number)
* [Installment Plan Search](../../doc/controllers/installment-plan.md#installment-plan-search)
* [Installment Plan Refund](../../doc/controllers/installment-plan.md#installment-plan-refund)


# Installment Plan Check Card Validity

```go
InstallmentPlanCheckCardValidity(
    ctx context.Context,
    body models.CardValidityRequest,
    xSplititTouchPoint *string,
    xSplititIdempotencyKey *string,
    xSplititTouchPointHeader *string,
    xSplititRequestID *string) (
    models.ApiResponse[models.CardValidityResponse],
    error)
```

## Authentication

This endpoint requires [OAuth2](../../doc/auth/oauth-2-client-credentials-grant.md) **AND** [ApiKey](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`models.CardValidityRequest`](../../doc/models/card-validity-request.md) | Body, Required | - |
| `xSplititTouchPoint` | `*string` | Header, Optional | - |
| `xSplititIdempotencyKey` | `*string` | Header, Optional | - |
| `xSplititTouchPointHeader` | `*string` | Header, Optional | Touch point string |
| `xSplititRequestID` | `*string` | Header, Optional | - |

## Requires scope

### OAuth2

`api.v4`

## Response Type

**200**: Success

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [models.CardValidityResponse](../../doc/models/card-validity-response.md).

## Example Usage

```go
ctx := context.Background()

body := models.CardValidityRequest{
}

apiResponse, err := installmentPlanController.InstallmentPlanCheckCardValidity(ctx, body, nil, nil, nil, nil)
if err != nil {
    switch typedErr := err.(type) {
        case *errors.ApiErrorResponse:
            log.Fatalln("ApiErrorResponseException: ", typedErr)
        default:
            log.Fatalln(err)
    }
} else {
    // Printing the result and response
    fmt.Println(apiResponse.Data)
    fmt.Println(apiResponse.Response.StatusCode)
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Error | [`ApiErrorResponseException`](../../doc/models/api-error-response-exception.md) |


# Installment Plan Create Offers

```go
InstallmentPlanCreateOffers(
    ctx context.Context,
    body models.OffersRequest,
    xSplititTouchPoint *string,
    xSplititIdempotencyKey *string,
    xSplititRequestID *string) (
    models.ApiResponse[models.OffersResponse],
    error)
```

## Authentication

This endpoint requires [OAuth2](../../doc/auth/oauth-2-client-credentials-grant.md) **AND** [ApiKey](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`models.OffersRequest`](../../doc/models/offers-request.md) | Body, Required | - |
| `xSplititTouchPoint` | `*string` | Header, Optional | Touch Point |
| `xSplititIdempotencyKey` | `*string` | Header, Optional | - |
| `xSplititRequestID` | `*string` | Header, Optional | - |

## Requires scope

### OAuth2

`api.v4`

## Response Type

**200**: Success

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [models.OffersResponse](../../doc/models/offers-response.md).

## Example Usage

```go
ctx := context.Background()

body := models.OffersRequest{
    PurchaseMethod:         models.PurchaseMethodEnum_INSTORE,
    PurchaseAmount:         "PurchaseAmount2",
    Currency:               "Currency4",
    ShopperDetails:         models.OffersShopperDetails{
        LastName:             "LastName6",
        Email:                "Email6",
    },
    PaymentMethod:          models.OffersPaymentMethod{
        Type:                 "Card",
        CardDetails:          models.OffersCardDetails{
            CardNumber:           "CardNumber2",
            ExpMonth:             90,
            ExpYear:              228,
        },
    },
}

apiResponse, err := installmentPlanController.InstallmentPlanCreateOffers(ctx, body, nil, nil, nil)
if err != nil {
    switch typedErr := err.(type) {
        case *errors.ApiErrorResponse:
            log.Fatalln("ApiErrorResponseException: ", typedErr)
        default:
            log.Fatalln(err)
    }
} else {
    // Printing the result and response
    fmt.Println(apiResponse.Data)
    fmt.Println(apiResponse.Response.StatusCode)
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Error | [`ApiErrorResponseException`](../../doc/models/api-error-response-exception.md) |


# Installment Plan Generate Payment Link

```go
InstallmentPlanGeneratePaymentLink(
    ctx context.Context,
    body models.PaymentLinkRequest,
    xSplititTouchPoint *string,
    xSplititIdempotencyKey *string,
    xSplititRequestID *string) (
    models.ApiResponse[models.PaymentLinkResponse],
    error)
```

## Authentication

This endpoint requires [OAuth2](../../doc/auth/oauth-2-client-credentials-grant.md) **AND** [ApiKey](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`models.PaymentLinkRequest`](../../doc/models/payment-link-request.md) | Body, Required | - |
| `xSplititTouchPoint` | `*string` | Header, Optional | Touch point and  version |
| `xSplititIdempotencyKey` | `*string` | Header, Optional | - |
| `xSplititRequestID` | `*string` | Header, Optional | - |

## Requires scope

### OAuth2

`api.v4`

## Response Type

**200**: Success

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [models.PaymentLinkResponse](../../doc/models/payment-link-response.md).

## Example Usage

```go
ctx := context.Background()

body := models.PaymentLinkRequest{
    Amount:                 "Amount8",
    Currency:               "Currency4",
    PurchaseMethod:         models.PurchaseMethodEnum_INSTORE,
    ShopperDetails:         models.OffersShopperDetails{
        LastName:             "LastName6",
        Email:                "Email6",
    },
}

apiResponse, err := installmentPlanController.InstallmentPlanGeneratePaymentLink(ctx, body, nil, nil, nil)
if err != nil {
    switch typedErr := err.(type) {
        case *errors.ApiErrorResponse:
            log.Fatalln("ApiErrorResponseException: ", typedErr)
        default:
            log.Fatalln(err)
    }
} else {
    // Printing the result and response
    fmt.Println(apiResponse.Data)
    fmt.Println(apiResponse.Response.StatusCode)
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Error | [`ApiErrorResponseException`](../../doc/models/api-error-response-exception.md) |


# Installment Plan Update Offers

```go
InstallmentPlanUpdateOffers(
    ctx context.Context,
    installmentPlanNumber string,
    body models.UpdateOffersRequest,
    xSplititTouchPoint *string,
    xSplititIdempotencyKey *string,
    xSplititRequestID *string) (
    models.ApiResponse[models.OffersResponse],
    error)
```

## Authentication

This endpoint requires [OAuth2](../../doc/auth/oauth-2-client-credentials-grant.md) **AND** [ApiKey](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `installmentPlanNumber` | `string` | Template, Required | - |
| `body` | [`models.UpdateOffersRequest`](../../doc/models/update-offers-request.md) | Body, Required | - |
| `xSplititTouchPoint` | `*string` | Header, Optional | Touch point and version |
| `xSplititIdempotencyKey` | `*string` | Header, Optional | - |
| `xSplititRequestID` | `*string` | Header, Optional | - |

## Requires scope

### OAuth2

`api.v4`

## Response Type

**200**: Success

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [models.OffersResponse](../../doc/models/offers-response.md).

## Example Usage

```go
ctx := context.Background()

installmentPlanNumber := "installmentPlanNumber6"

body := models.UpdateOffersRequest{
}

apiResponse, err := installmentPlanController.InstallmentPlanUpdateOffers(ctx, installmentPlanNumber, body, nil, nil, nil)
if err != nil {
    switch typedErr := err.(type) {
        case *errors.ApiErrorResponse:
            log.Fatalln("ApiErrorResponseException: ", typedErr)
        default:
            log.Fatalln(err)
    }
} else {
    // Printing the result and response
    fmt.Println(apiResponse.Data)
    fmt.Println(apiResponse.Response.StatusCode)
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Error | [`ApiErrorResponseException`](../../doc/models/api-error-response-exception.md) |


# Installment Plan Authorize

```go
InstallmentPlanAuthorize(
    ctx context.Context,
    installmentPlanNumber string,
    body models.AuthorizeRequest,
    xSplititTouchPoint *string,
    xSplititIdempotencyKey *string,
    xSplititRequestID *string) (
    models.ApiResponse[models.AuthorizeResponse],
    error)
```

## Authentication

This endpoint requires [OAuth2](../../doc/auth/oauth-2-client-credentials-grant.md) **AND** [ApiKey](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `installmentPlanNumber` | `string` | Template, Required | - |
| `body` | [`models.AuthorizeRequest`](../../doc/models/authorize-request.md) | Body, Required | - |
| `xSplititTouchPoint` | `*string` | Header, Optional | Touch point and version |
| `xSplititIdempotencyKey` | `*string` | Header, Optional | - |
| `xSplititRequestID` | `*string` | Header, Optional | - |

## Requires scope

### OAuth2

`api.v4`

## Response Type

**200**: Success

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [models.AuthorizeResponse](../../doc/models/authorize-response.md).

## Example Usage

```go
ctx := context.Background()

installmentPlanNumber := "installmentPlanNumber6"

body := models.AuthorizeRequest{
    OfferId:                "OfferId8",
    AutoCapture:            false,
    ShopperAcceptedTerms:   false,
}

apiResponse, err := installmentPlanController.InstallmentPlanAuthorize(ctx, installmentPlanNumber, body, nil, nil, nil)
if err != nil {
    switch typedErr := err.(type) {
        case *errors.ApiErrorResponse:
            log.Fatalln("ApiErrorResponseException: ", typedErr)
        default:
            log.Fatalln(err)
    }
} else {
    // Printing the result and response
    fmt.Println(apiResponse.Data)
    fmt.Println(apiResponse.Response.StatusCode)
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Error | [`ApiErrorResponseException`](../../doc/models/api-error-response-exception.md) |


# Installment Plan Update Order

```go
InstallmentPlanUpdateOrder(
    ctx context.Context,
    installmentPlanNumber string,
    body models.UpdateOrderRequest,
    xSplititTouchPoint *string,
    xSplititIdempotencyKey *string,
    xSplititRequestID *string) (
    models.ApiResponse[models.UpdateOrderResponse],
    error)
```

## Authentication

This endpoint requires [OAuth2](../../doc/auth/oauth-2-client-credentials-grant.md) **AND** [ApiKey](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `installmentPlanNumber` | `string` | Template, Required | - |
| `body` | [`models.UpdateOrderRequest`](../../doc/models/update-order-request.md) | Body, Required | - |
| `xSplititTouchPoint` | `*string` | Header, Optional | Touch point and version |
| `xSplititIdempotencyKey` | `*string` | Header, Optional | - |
| `xSplititRequestID` | `*string` | Header, Optional | - |

## Requires scope

### OAuth2

`api.v4`

## Response Type

**200**: Success

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [models.UpdateOrderResponse](../../doc/models/update-order-response.md).

## Example Usage

```go
ctx := context.Background()

installmentPlanNumber := "installmentPlanNumber6"

body := models.UpdateOrderRequest{
    ShippingStatus:         models.ShippingStatusEnum_DELIVERED,
}

apiResponse, err := installmentPlanController.InstallmentPlanUpdateOrder(ctx, installmentPlanNumber, body, nil, nil, nil)
if err != nil {
    switch typedErr := err.(type) {
        case *errors.ApiErrorResponse:
            log.Fatalln("ApiErrorResponseException: ", typedErr)
        default:
            log.Fatalln(err)
    }
} else {
    // Printing the result and response
    fmt.Println(apiResponse.Data)
    fmt.Println(apiResponse.Response.StatusCode)
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Error | [`ApiErrorResponseException`](../../doc/models/api-error-response-exception.md) |


# Installment Plan Get by Installment Plan Number

```go
InstallmentPlanGetByInstallmentPlanNumber(
    ctx context.Context,
    installmentPlanNumber string,
    xSplititTouchPoint *string,
    xSplititIdempotencyKey *string,
    xSplititRequestID *string) (
    models.ApiResponse[models.InstallmentPlanDetailsResponse],
    error)
```

## Authentication

This endpoint requires [OAuth2](../../doc/auth/oauth-2-client-credentials-grant.md) **AND** [ApiKey](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `installmentPlanNumber` | `string` | Template, Required | - |
| `xSplititTouchPoint` | `*string` | Header, Optional | Touch point and version |
| `xSplititIdempotencyKey` | `*string` | Header, Optional | - |
| `xSplititRequestID` | `*string` | Header, Optional | - |

## Requires scope

### OAuth2

`api.v4`

## Response Type

**200**: Success

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [models.InstallmentPlanDetailsResponse](../../doc/models/installment-plan-details-response.md).

## Example Usage

```go
ctx := context.Background()

installmentPlanNumber := "installmentPlanNumber6"

apiResponse, err := installmentPlanController.InstallmentPlanGetByInstallmentPlanNumber(ctx, installmentPlanNumber, nil, nil, nil)
if err != nil {
    switch typedErr := err.(type) {
        case *errors.ApiErrorResponse:
            log.Fatalln("ApiErrorResponseException: ", typedErr)
        default:
            log.Fatalln(err)
    }
} else {
    // Printing the result and response
    fmt.Println(apiResponse.Data)
    fmt.Println(apiResponse.Response.StatusCode)
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Error | [`ApiErrorResponseException`](../../doc/models/api-error-response-exception.md) |


# Installment Plan Search

```go
InstallmentPlanSearch(
    ctx context.Context,
    body models.InstallmentPlanSearchRequest,
    xSplititTouchPoint *string,
    xSplititIdempotencyKey *string,
    xSplititRequestID *string) (
    models.ApiResponse[models.InstallmentPlanSearchDetailsResponse],
    error)
```

## Authentication

This endpoint requires [OAuth2](../../doc/auth/oauth-2-client-credentials-grant.md) **AND** [ApiKey](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`models.InstallmentPlanSearchRequest`](../../doc/models/installment-plan-search-request.md) | Body, Required | - |
| `xSplititTouchPoint` | `*string` | Header, Optional | Touch point and version |
| `xSplititIdempotencyKey` | `*string` | Header, Optional | - |
| `xSplititRequestID` | `*string` | Header, Optional | - |

## Requires scope

### OAuth2

`api.v4`

## Response Type

**200**: Success

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [models.InstallmentPlanSearchDetailsResponse](../../doc/models/installment-plan-search-details-response.md).

## Example Usage

```go
ctx := context.Background()

body := models.InstallmentPlanSearchRequest{
}

apiResponse, err := installmentPlanController.InstallmentPlanSearch(ctx, body, nil, nil, nil)
if err != nil {
    switch typedErr := err.(type) {
        case *errors.ApiErrorResponse:
            log.Fatalln("ApiErrorResponseException: ", typedErr)
        default:
            log.Fatalln(err)
    }
} else {
    // Printing the result and response
    fmt.Println(apiResponse.Data)
    fmt.Println(apiResponse.Response.StatusCode)
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Error | [`ApiErrorResponseException`](../../doc/models/api-error-response-exception.md) |


# Installment Plan Refund

```go
InstallmentPlanRefund(
    ctx context.Context,
    installmentPlanNumber string,
    body models.RefundRequest,
    xSplititTouchPoint *string,
    xSplititIdempotencyKey *string,
    xSplititRequestID *string) (
    models.ApiResponse[models.RefundResponse],
    error)
```

## Authentication

This endpoint requires [OAuth2](../../doc/auth/oauth-2-client-credentials-grant.md) **AND** [ApiKey](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `installmentPlanNumber` | `string` | Template, Required | - |
| `body` | [`models.RefundRequest`](../../doc/models/refund-request.md) | Body, Required | - |
| `xSplititTouchPoint` | `*string` | Header, Optional | Touch point and version |
| `xSplititIdempotencyKey` | `*string` | Header, Optional | - |
| `xSplititRequestID` | `*string` | Header, Optional | - |

## Requires scope

### OAuth2

`api.v4`

## Response Type

**200**: Success

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [models.RefundResponse](../../doc/models/refund-response.md).

## Example Usage

```go
ctx := context.Background()

installmentPlanNumber := "installmentPlanNumber6"

body := models.RefundRequest{
    Amount:               "Amount8",
}

apiResponse, err := installmentPlanController.InstallmentPlanRefund(ctx, installmentPlanNumber, body, nil, nil, nil)
if err != nil {
    switch typedErr := err.(type) {
        case *errors.ApiErrorResponse:
            log.Fatalln("ApiErrorResponseException: ", typedErr)
        default:
            log.Fatalln(err)
    }
} else {
    // Printing the result and response
    fmt.Println(apiResponse.Data)
    fmt.Println(apiResponse.Response.StatusCode)
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Error | [`ApiErrorResponseException`](../../doc/models/api-error-response-exception.md) |

