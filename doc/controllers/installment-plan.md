# Installment Plan

```csharp
InstallmentPlanController installmentPlanController = client.InstallmentPlanController;
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

```csharp
InstallmentPlanGetAsync(
    string installmentPlanNumber,
    string xSplititTouchPoint = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `installmentPlanNumber` | `string` | Template, Required | - |
| `xSplititTouchPoint` | `string` | Header, Optional | TouchPoint |

## Requires scope

### OAuth2-sandbox

`api.v3`

### OAuth2-production

`api.v3`

## Response Type

[`Task<Models.InstallmentPlanGetResponse>`](../../doc/models/installment-plan-get-response.md)

## Example Usage

```csharp
string installmentPlanNumber = "installmentPlanNumber6";
try
{
    InstallmentPlanGetResponse result = await installmentPlanController.InstallmentPlanGetAsync(installmentPlanNumber);
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
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

```csharp
InstallmentPlanSearchAsync(
    string installmentPlanNumber = null,
    string refOrderNumber = null,
    object extendedParams = null,
    string xSplititTouchPoint = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `installmentPlanNumber` | `string` | Query, Optional | - |
| `refOrderNumber` | `string` | Query, Optional | - |
| `extendedParams` | `object` | Query, Optional | - |
| `xSplititTouchPoint` | `string` | Header, Optional | TouchPoint |

## Requires scope

### OAuth2-sandbox

`api.v3`

### OAuth2-production

`api.v3`

## Response Type

[`Task<Models.InstallmentPlanSearchResponse>`](../../doc/models/installment-plan-search-response.md)

## Example Usage

```csharp
try
{
    InstallmentPlanSearchResponse result = await installmentPlanController.InstallmentPlanSearchAsync();
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
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

```csharp
InstallmentPlanPostAsync(
    string xSplititIdempotencyKey,
    Models.InstallmentPlanInitiateRequest body,
    Models.TestModesEnum? xSplititTestMode = null,
    string xSplititTouchPoint = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `xSplititIdempotencyKey` | `string` | Header, Required | - |
| `body` | [`InstallmentPlanInitiateRequest`](../../doc/models/installment-plan-initiate-request.md) | Body, Required | - |
| `xSplititTestMode` | [`TestModesEnum?`](../../doc/models/test-modes-enum.md) | Header, Optional | - |
| `xSplititTouchPoint` | `string` | Header, Optional | TouchPoint |

## Requires scope

### OAuth2-sandbox

`api.v3`

### OAuth2-production

`api.v3`

## Response Type

[`Task<Models.InitiatePlanResponse>`](../../doc/models/initiate-plan-response.md)

## Example Usage

```csharp
string xSplititIdempotencyKey = "X-Splitit-IdempotencyKey2";
InstallmentPlanInitiateRequest body = new InstallmentPlanInitiateRequest
{
};

try
{
    InitiatePlanResponse result = await installmentPlanController.InstallmentPlanPostAsync(
        xSplititIdempotencyKey,
        body
    );
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
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

```csharp
InstallmentPlanPost2Async(
    string xSplititIdempotencyKey,
    Models.InstallmentPlanCreateRequest body,
    Models.TestModesEnum? xSplititTestMode = null,
    string xSplititTouchPoint = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `xSplititIdempotencyKey` | `string` | Header, Required | - |
| `body` | [`InstallmentPlanCreateRequest`](../../doc/models/installment-plan-create-request.md) | Body, Required | - |
| `xSplititTestMode` | [`TestModesEnum?`](../../doc/models/test-modes-enum.md) | Header, Optional | - |
| `xSplititTouchPoint` | `string` | Header, Optional | TouchPoint |

## Requires scope

### OAuth2-sandbox

`api.v3`

### OAuth2-production

`api.v3`

## Response Type

[`Task<Models.InstallmentPlanCreateResponse>`](../../doc/models/installment-plan-create-response.md)

## Example Usage

```csharp
string xSplititIdempotencyKey = "X-Splitit-IdempotencyKey2";
InstallmentPlanCreateRequest body = new InstallmentPlanCreateRequest
{
    AutoCapture = false,
    TermsAndConditionsAccepted = false,
};

try
{
    InstallmentPlanCreateResponse result = await installmentPlanController.InstallmentPlanPost2Async(
        xSplititIdempotencyKey,
        body
    );
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
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

```csharp
InstallmentPlanVerifyAuthorizationAsync(
    string installmentPlanNumber,
    string xSplititTouchPoint = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `installmentPlanNumber` | `string` | Template, Required | - |
| `xSplititTouchPoint` | `string` | Header, Optional | TouchPoint |

## Requires scope

### OAuth2-sandbox

`api.v3`

### OAuth2-production

`api.v3`

## Response Type

[`Task<Models.VerifyAuthorizationResponse>`](../../doc/models/verify-authorization-response.md)

## Example Usage

```csharp
string installmentPlanNumber = "installmentPlanNumber6";
try
{
    VerifyAuthorizationResponse result = await installmentPlanController.InstallmentPlanVerifyAuthorizationAsync(installmentPlanNumber);
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
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

```csharp
InstallmentPlanUpdateOrderAsync(
    string installmentPlanNumber,
    string xSplititIdempotencyKey,
    Models.InstallmentPlanUpdateRequest body,
    string xSplititTouchPoint = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `installmentPlanNumber` | `string` | Template, Required | - |
| `xSplititIdempotencyKey` | `string` | Header, Required | - |
| `body` | [`InstallmentPlanUpdateRequest`](../../doc/models/installment-plan-update-request.md) | Body, Required | - |
| `xSplititTouchPoint` | `string` | Header, Optional | TouchPoint |

## Requires scope

### OAuth2-sandbox

`api.v3`

### OAuth2-production

`api.v3`

## Response Type

[`Task<Models.InstallmentPlanUpdateResponse>`](../../doc/models/installment-plan-update-response.md)

## Example Usage

```csharp
string installmentPlanNumber = "installmentPlanNumber6";
string xSplititIdempotencyKey = "X-Splitit-IdempotencyKey2";
InstallmentPlanUpdateRequest body = new InstallmentPlanUpdateRequest
{
};

try
{
    InstallmentPlanUpdateResponse result = await installmentPlanController.InstallmentPlanUpdateOrderAsync(
        installmentPlanNumber,
        xSplititIdempotencyKey,
        body
    );
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
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

```csharp
InstallmentPlanUpdateOrder2Async(
    string xSplititIdempotencyKey,
    Models.InstallmentPlanUpdateRequestByIdentifier body,
    string xSplititTouchPoint = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `xSplititIdempotencyKey` | `string` | Header, Required | - |
| `body` | [`InstallmentPlanUpdateRequestByIdentifier`](../../doc/models/installment-plan-update-request-by-identifier.md) | Body, Required | - |
| `xSplititTouchPoint` | `string` | Header, Optional | TouchPoint |

## Requires scope

### OAuth2-sandbox

`api.v3`

### OAuth2-production

`api.v3`

## Response Type

[`Task<Models.InstallmentPlanUpdateResponse>`](../../doc/models/installment-plan-update-response.md)

## Example Usage

```csharp
string xSplititIdempotencyKey = "X-Splitit-IdempotencyKey2";
InstallmentPlanUpdateRequestByIdentifier body = new InstallmentPlanUpdateRequestByIdentifier
{
};

try
{
    InstallmentPlanUpdateResponse result = await installmentPlanController.InstallmentPlanUpdateOrder2Async(
        xSplititIdempotencyKey,
        body
    );
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
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

```csharp
InstallmentPlanRefundAsync(
    string installmentPlanNumber,
    string xSplititIdempotencyKey,
    Models.InstallmentPlanRefundRequest body,
    string xSplititTouchPoint = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `installmentPlanNumber` | `string` | Template, Required | - |
| `xSplititIdempotencyKey` | `string` | Header, Required | - |
| `body` | [`InstallmentPlanRefundRequest`](../../doc/models/installment-plan-refund-request.md) | Body, Required | - |
| `xSplititTouchPoint` | `string` | Header, Optional | TouchPoint |

## Requires scope

### OAuth2-sandbox

`api.v3`

### OAuth2-production

`api.v3`

## Response Type

[`Task<Models.InstallmentPlanRefundResponse>`](../../doc/models/installment-plan-refund-response.md)

## Example Usage

```csharp
string installmentPlanNumber = "installmentPlanNumber6";
string xSplititIdempotencyKey = "X-Splitit-IdempotencyKey2";
InstallmentPlanRefundRequest body = new InstallmentPlanRefundRequest
{
    Amount = "Amount8",
};

try
{
    InstallmentPlanRefundResponse result = await installmentPlanController.InstallmentPlanRefundAsync(
        installmentPlanNumber,
        xSplititIdempotencyKey,
        body
    );
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
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

```csharp
InstallmentPlanCheckEligibilityAsync(
    string xSplititIdempotencyKey,
    Models.CheckInstallmentsEligibilityRequest body,
    string xSplititTouchPoint = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `xSplititIdempotencyKey` | `string` | Header, Required | - |
| `body` | [`CheckInstallmentsEligibilityRequest`](../../doc/models/check-installments-eligibility-request.md) | Body, Required | - |
| `xSplititTouchPoint` | `string` | Header, Optional | TouchPoint |

## Requires scope

### OAuth2-sandbox

`api.v3`

### OAuth2-production

`api.v3`

## Response Type

[`Task<Models.InstallmentsEligibilityResponse>`](../../doc/models/installments-eligibility-response.md)

## Example Usage

```csharp
string xSplititIdempotencyKey = "X-Splitit-IdempotencyKey2";
CheckInstallmentsEligibilityRequest body = new CheckInstallmentsEligibilityRequest
{
};

try
{
    InstallmentsEligibilityResponse result = await installmentPlanController.InstallmentPlanCheckEligibilityAsync(
        xSplititIdempotencyKey,
        body
    );
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
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

```csharp
InstallmentPlanGetEligibilityTermsAndConditionAsync(
    string ipn,
    string xSplititTouchPoint = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ipn` | `string` | Template, Required | - |
| `xSplititTouchPoint` | `string` | Header, Optional | TouchPoint |

## Requires scope

### OAuth2-sandbox

`api.v3`

### OAuth2-production

`api.v3`

## Response Type

[`Task<Models.EligibilityTermsAndConditionResponse>`](../../doc/models/eligibility-terms-and-condition-response.md)

## Example Usage

```csharp
string ipn = "ipn4";
try
{
    EligibilityTermsAndConditionResponse result = await installmentPlanController.InstallmentPlanGetEligibilityTermsAndConditionAsync(ipn);
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 403 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 404 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |
| 500 | - | [`FailedResponseException`](../../doc/models/failed-response-exception.md) |

