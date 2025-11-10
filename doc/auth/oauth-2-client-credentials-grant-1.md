
# OAuth 2 Client Credentials Grant



Documentation for accessing and setting credentials for OAuth2-production.

## Auth Credentials

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| OAuthClientId | `string` | OAuth 2 Client ID | `OAuthClientId` | `OAuthClientId` |
| OAuthClientSecret | `string` | OAuth 2 Client Secret | `OAuthClientSecret` | `OAuthClientSecret` |
| OAuthToken | `Models.OAuthToken` | Object for storing information about the OAuth token | `OAuthToken` | `OAuthToken` |
| OAuthScopes | `List<Models.OAuthScopeOAuth2ProductionEnum>` | List of scopes that apply to the OAuth token | `OAuthScopes` | `OAuthScopes` |
| OAuthClockSkew | `TimeSpan?` | Clock skew time in seconds applied while checking the OAuth Token expiry. | `OAuthClockSkew` | `OAuthClockSkew` |
| OAuthTokenProvider | `Func<OAuth2ProductionManager, OAuthToken, Task<OAuthToken>>` | Registers a callback for oAuth Token Provider used for automatic token fetching/refreshing. | `OAuthTokenProvider` | `OAuthTokenProvider` |
| OAuthOnTokenUpdate | `Action<OAuthToken>` | Registers a callback for token update event. | `OAuthOnTokenUpdate` | `OAuthOnTokenUpdate` |



**Note:** Auth credentials can be set using `OAuth2ProductionCredentials` in the client builder and accessed through `OAuth2ProductionCredentials` method in the client instance.

## Usage Example

### Client Initialization

You must initialize the client with *OAuth 2.0 Client Credentials Grant* credentials as shown in the following code snippet. This will fetch the OAuth token automatically when any of the endpoints, requiring *OAuth 2.0 Client Credentials Grant* authentication, are called.

```csharp
using SplititWebApiV3.Standard;
using SplititWebApiV3.Standard.Authentication;

namespace ConsoleApp;

SplititWebApiV3Client client = new SplititWebApiV3Client.Builder()
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
    .Build();
```



Your application can also manually provide an OAuthToken using the setter `oAuthToken` in `OAuth2ProductionModel` object. This function takes in an instance of OAuthToken containing information for authorizing client requests and refreshing the token itself.

You must have initialized the client with scopes for which you need permission to access.

### Scopes

Scopes enable your application to only request access to the resources it needs while enabling users to control the amount of access they grant to your application. Available scopes are defined in the [`OAuthScopeOAuth2ProductionEnum`](../../doc/models/o-auth-scope-o-auth-2-production-enum.md) enumeration.

| Scope Name | Description |
|  --- | --- |
| `API.V3` | Access to WebAPI version 3 |

### Adding OAuth Token Update Callback

Whenever the OAuth Token gets updated, the provided callback implementation will be executed. For instance, you may use it to store your access token whenever it gets updated.

```csharp
using SplititWebApiV3.Standard;
using SplititWebApiV3.Standard.Authentication;

namespace ConsoleApp;

SplititWebApiV3Client client = new SplititWebApiV3Client.Builder()
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
        .OAuthOnTokenUpdate(token => 
        {
            // It will be triggered whenever the token gets updated
            SaveTokenToDatabase(token);
        })
        .Build())
    .Build();
```

### Adding Custom OAuth Token Provider

To authorize a client using a stored access token, set up the `oAuthTokenProvider` in `OAuth2ProductionModel` builder along with the other auth parameters before creating the client:

```csharp
using SplititWebApiV3.Standard;
using SplititWebApiV3.Standard.Authentication;

namespace ConsoleApp;

SplititWebApiV3Client client = new SplititWebApiV3Client.Builder()
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
        .OAuthTokenProvider(async (credentialsManager, token) =>
        {
            // Add the callback handler to provide a new OAuth token
            // It will be triggered whenever the token is undefined or expired
            return LoadTokenFromDatabase() ?? await credentialsManager.FetchTokenAsync();
        })
        .Build())
    .Build();
```


