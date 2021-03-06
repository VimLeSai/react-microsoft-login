# react-microsoft-login

>React component for login with Microsoft services using OAuth. Check [demo here](https://alexandrtovmach.github.io/react-microsoft-login/).

[![NPM](https://nodei.co/npm/react-microsoft-login.png)](https://www.npmjs.com/package/react-microsoft-login)

## Get started
1. Install package: 
    ```
    yarn add react-microsoft-login
    ```
2. Import and configure component:
    ```
    import React from "react";
    import MicrosoftLogin from "react-microsoft-login";

    export default props => {
        
        const authHandler = (err, data) => {
            console.log(err, data)
        }
        
        return (
            <MicrosoftLogin
                clientId={YOUR_CLIENT_ID}
                authCallback={authHandler}
            />
        )
    }

    ```
3. `YOUR_CLIENT_ID` is the key which you need to generate for your Microsoft app. [How to create Microsoft app?](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-v2-register-an-app) When finished, on the app Overview page, note down the Application (client) ID value.


## API

| Parameter     | Type       | Default         | Description                                                     |
|---------------|------------|-----------------|-----------------------------------------------------------------|
| clientId      | string     | required        | Application (client) ID                                         |
| authCallback  | function   | required        | Callback function which takes two arguments `(error, authData)` |
| graphScopes   | array      | `["user.read"]` | Array of Graph API permission names. [More about Graph API permissions](https://developer.microsoft.com/en-us/graph/docs/concepts/permissions_reference).|
| tenantUrl     | string     | `""`            | A URL indicating a directory that MSAL can request tokens from. [More about MSAL tenant auth](https://github.com/AzureAD/microsoft-authentication-library-for-js/wiki/MSAL-basics).|
| buttonTheme   | string     | `"light"`       | Name of theme for button style. Themes: `"light"` `"light_short"` `"dark"` `"dark_short"`. Styles come from [Official Microsoft brand design](https://docs.microsoft.com/en-us/azure/active-directory/develop/howto-add-branding-in-azure-ad-apps).|
| withUserData  | boolean    | `false`         | Boolean flag to make an additional request to GraphAPI to get user data. |
| debug         | boolean    | `false`         | Boolean flag to enable detailed logs of authorization process. |
| className     | string     | `""`            | Additional class name string. |

  


## To do
1. ~~Add regex validation for clientId~~
2. ~~Research about possibility to add validation for graph scopes~~
3. ~~Finish implementing support for IE and Edge~~
4. Check possibilities of design customisation

## License

[MIT](https://github.com/nishanths/license/blob/master/LICENSE)
