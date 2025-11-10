
# Getting Started with splitit-web-api-v3

## Install the Package

If you are building with .NET CLI tools then you can also use the following command:

```bash
dotnet add package Splitit.InstallmentsSDK --version 1.0.5
```

You can also view the package at:
https://www.nuget.org/packages/Splitit.InstallmentsSDK/1.0.5

## Test the SDK

The generated SDK also contain one or more Tests, which are contained in the Tests project. In order to invoke these test cases, you will need `NUnit 3.0 Test Adapter Extension` for Visual Studio. Once the SDK is complied, the test cases should appear in the Test Explorer window. Here, you can click `Run All` to execute these test cases.

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](https://www.github.com/Splitit/.NET-C-SDK/tree/1.0.5/doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| Environment | `Environment` | The API environment. <br> **Default: `Environment.Production`** |
| Timeout | `TimeSpan` | Http client timeout.<br>*Default*: `TimeSpan.FromSeconds(100)` |
| HttpClientConfiguration | [`Action<HttpClientConfiguration.Builder>`](https://www.github.com/Splitit/.NET-C-SDK/tree/1.0.5/doc/http-client-configuration-builder.md) | Action delegate that configures the HTTP client by using the HttpClientConfiguration.Builder for customizing API call settings.<br>*Default*: `new HttpClient()` |
| OAuth2SandboxCredentials | [`OAuth2SandboxCredentials`](https://www.github.com/Splitit/.NET-C-SDK/tree/1.0.5/doc/auth/oauth-2-client-credentials-grant.md) | The Credentials Setter for OAuth 2 Client Credentials Grant |
| OAuth2ProductionCredentials | [`OAuth2ProductionCredentials`](https://www.github.com/Splitit/.NET-C-SDK/tree/1.0.5/doc/auth/oauth-2-client-credentials-grant-1.md) | The Credentials Setter for OAuth 2 Client Credentials Grant |

The API client can be initialized as follows:

```csharp
using SplititWebApiV3.Standard;
using SplititWebApiV3.Standard.Authentication;
using SplititWebApiV3.Standard.Models;
using System.Collections.Generic;

namespace ConsoleApp;

SplititWebApiV3Client client = new SplititWebApiV3Client.Builder()
    .OAuth2SandboxCredentials(
        new OAuth2SandboxModel.Builder(
            "OAuthClientId",
            "OAuthClientSecret"
        )
        .OAuthScopes(
            new List<OAuthScopeOAuth2SandboxEnum>
            {
                OAuthScopeOAuth2SandboxEnum.ApiV3,
            })
        .Build())
    .OAuth2ProductionCredentials(
        new OAuth2ProductionModel.Builder(
            "OAuthClientId",
            "OAuthClientSecret"
        )
        .OAuthScopes(
            new List<OAuthScopeOAuth2ProductionEnum>
            {
                OAuthScopeOAuth2ProductionEnum.ApiV3,
            })
        .Build())
    .Environment(SplititWebApiV3.Standard.Environment.Production)
    .Build();
```

## Environments

The SDK can be configured to use a different environment for making API calls. Available environments are:

### Fields

| Name | Description |
|  --- | --- |
| production | **Default** Sandbox |
| environment2 | Production |

## Authorization

This API uses the following authentication schemes.

* [`OAuth2-sandbox (OAuth 2 Client Credentials Grant)`](https://www.github.com/Splitit/.NET-C-SDK/tree/1.0.5/doc/auth/oauth-2-client-credentials-grant.md)
* [`OAuth2-production (OAuth 2 Client Credentials Grant)`](https://www.github.com/Splitit/.NET-C-SDK/tree/1.0.5/doc/auth/oauth-2-client-credentials-grant-1.md)

## List of APIs

* [Installment Plan](https://www.github.com/Splitit/.NET-C-SDK/tree/1.0.5/doc/controllers/installment-plan.md)

## SDK Infrastructure

### Configuration

* [HttpClientConfiguration](https://www.github.com/Splitit/.NET-C-SDK/tree/1.0.5/doc/http-client-configuration.md)
* [HttpClientConfigurationBuilder](https://www.github.com/Splitit/.NET-C-SDK/tree/1.0.5/doc/http-client-configuration-builder.md)
* [ProxyConfigurationBuilder](https://www.github.com/Splitit/.NET-C-SDK/tree/1.0.5/doc/proxy-configuration-builder.md)

### HTTP

* [HttpCallback](https://www.github.com/Splitit/.NET-C-SDK/tree/1.0.5/doc/http-callback.md)
* [HttpContext](https://www.github.com/Splitit/.NET-C-SDK/tree/1.0.5/doc/http-context.md)
* [HttpRequest](https://www.github.com/Splitit/.NET-C-SDK/tree/1.0.5/doc/http-request.md)
* [HttpResponse](https://www.github.com/Splitit/.NET-C-SDK/tree/1.0.5/doc/http-response.md)
* [HttpStringResponse](https://www.github.com/Splitit/.NET-C-SDK/tree/1.0.5/doc/http-string-response.md)

### Utilities

* [ApiException](https://www.github.com/Splitit/.NET-C-SDK/tree/1.0.5/doc/api-exception.md)
* [ApiHelper](https://www.github.com/Splitit/.NET-C-SDK/tree/1.0.5/doc/api-helper.md)
* [CustomDateTimeConverter](https://www.github.com/Splitit/.NET-C-SDK/tree/1.0.5/doc/custom-date-time-converter.md)
* [UnixDateTimeConverter](https://www.github.com/Splitit/.NET-C-SDK/tree/1.0.5/doc/unix-date-time-converter.md)

