
# Client Class Documentation

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| Environment | `Environment` | The API environment. <br> **Default: `Environment.Production`** |
| Timeout | `TimeSpan` | Http client timeout.<br>*Default*: `TimeSpan.FromSeconds(100)` |
| HttpClientConfiguration | [`Action<HttpClientConfiguration.Builder>`](../doc/http-client-configuration-builder.md) | Action delegate that configures the HTTP client by using the HttpClientConfiguration.Builder for customizing API call settings.<br>*Default*: `new HttpClient()` |
| OAuth2SandboxCredentials | [`OAuth2SandboxCredentials`](auth/oauth-2-client-credentials-grant.md) | The Credentials Setter for OAuth 2 Client Credentials Grant |
| OAuth2ProductionCredentials | [`OAuth2ProductionCredentials`](auth/oauth-2-client-credentials-grant-1.md) | The Credentials Setter for OAuth 2 Client Credentials Grant |

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

## splitit-web-api-v3Client Class

The gateway for the SDK. This class acts as a factory for the Controllers and also holds the configuration of the SDK.

### Controllers

| Name | Description |
|  --- | --- |
| InstallmentPlanController | Gets InstallmentPlanController controller. |
| OAuthAuthorizationController | Gets OAuthAuthorizationController controller. |

### Properties

| Name | Description | Type |
|  --- | --- | --- |
| HttpClientConfiguration | Gets the configuration of the Http Client associated with this client. | [`IHttpClientConfiguration`](../doc/http-client-configuration.md) |
| Timeout | Http client timeout. | `TimeSpan` |
| Environment | Current API environment. | `Environment` |
| OAuth2SandboxCredentials | Gets the credentials to use with OAuth2Sandbox. | [`IOAuth2SandboxCredentials`](auth/oauth-2-client-credentials-grant.md) |
| OAuth2ProductionCredentials | Gets the credentials to use with OAuth2Production. | [`IOAuth2ProductionCredentials`](auth/oauth-2-client-credentials-grant-1.md) |

### Methods

| Name | Description | Return Type |
|  --- | --- | --- |
| `GetBaseUri(Server alias = Server.Default)` | Gets the URL for a particular alias in the current environment and appends it with template parameters. | `string` |
| `ToBuilder()` | Creates an object of the splitit-web-api-v3Client using the values provided for the builder. | `Builder` |

## splitit-web-api-v3Client Builder Class

Class to build instances of splitit-web-api-v3Client.

### Methods

| Name | Description | Return Type |
|  --- | --- | --- |
| `HttpClientConfiguration(Action<`[`HttpClientConfiguration.Builder`](../doc/http-client-configuration-builder.md)`> action)` | Gets the configuration of the Http Client associated with this client. | `Builder` |
| `Timeout(TimeSpan timeout)` | Http client timeout. | `Builder` |
| `Environment(Environment environment)` | Current API environment. | `Builder` |
| `OAuth2SandboxCredentials(Action<OAuth2SandboxModel.Builder> action)` | Sets credentials for OAuth2Sandbox. | `Builder` |
| `OAuth2ProductionCredentials(Action<OAuth2ProductionModel.Builder> action)` | Sets credentials for OAuth2Production. | `Builder` |

