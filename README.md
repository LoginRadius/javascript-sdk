# Javascript SDK 

![Home Image](https://docs.lrcontent.com/resources/github/banner-1544x500.png)

Introduction
=====

Customer Identity public repo for the LoginRadius JS SDK, based on LoginRadius V2 APIs.

LoginRadius is an Identity Management Platform that simplifies user registration while securing data. LoginRadius Platform simplifies and secures your user registration process, increases conversion with Social Login that combines 30 major social platforms, and offers a full solution with Traditional User Registration. You can gather a wealth of user profile data from Social Login or Traditional User Registration.

LoginRadius centralizes it all in one place, making it easy to manage and access. Easily integrate LoginRadius with all of your third-party applications, like MailChimp, Google Analytics, Livefyre and many more, making it easy to utilize the data you are capturing.

LoginRadius helps businesses boost user engagement on their web/mobile platform, manage online identities, utilize social media for marketing, capture accurate consumer data, and get unique social insight into their customer base.

Please visit [here](http://www.loginradius.com/) for more information.

>Disclaimer<br>
>This library is meant to help you with a quick implementation of the LoginRadius platform and also to serve as a reference point for the LoginRadius API. Keep in mind that it is an open source library, which means you are free to download and customize the library functions based on your specific application needs.

## Installation
In order to utilize the LoginRadius JS SDK, you will need to initialize the SDK with the following configurations:

```
import initializeSDKClient from './LoginRadius_JS_SDK.js'

    LoginRadiusSDK = new initializeSDKClient({
      appName: {{Required | YOUR App Name}},
      apiKey: {{Required | YOUR API KEY}},
      customDomain: {{Optional | custom domain name, default is hub.loginradius.com}}
      apiDomain: {{Optional | Api endpoint , default is https://api.loginradius.com}}
      debugMode: {{Optional| true/false}}

    });
```

Replace the placeholders with your LoginRadius credentials **apikey**, **appName**. These can be obtained from [here](https://www.loginradius.com/docs/api/v2/admin-console/platform-security/api-key-and-secret).

Pass **customDomain** and **apiDomain** if you have these enabled for your app. 

While in developement you can enable the **debugMode** to debug in browser developer console. 

## Getting Started

This document contains the information of methods supported by LoginRadius Javascript SDK.

### openLoginPage()

This method redirects the user to the LoginRadius IDX page. 

```
LoginRadiusSDK.openLoginPage({
        redirect_uri: window.location.href
    });
```

### appCallback()

This method fetches the token from query string and store it in browser storage

```
LoginRadiusSDK.appCallback()
```

### isLoggedIn()

This method checks whether the user is logged in or not, and returns a boolean value

```
LoginRadiusSDK.isLoggedIn()
```

### logout()

This method triggers logout action

```
LoginRadiusSDK.logout({
        returnTo: window.location.href
    });
```

Here returnTo is the return url, where the user will be redirected after successful logout.

### openRegisterPage()

This method triggers registration action and redirects to the LoginRadius IDX registration section.

```
 LoginRadiusSDK.openRegisterPage({
        redirect_uri: window.location.href
    });
```

Here redirect_uri is the return url, where the user will be redirected after a successful registration.

### profileUpdate()

This method redirects to LoginRadius IDX profile.aspx page.

```
LoginRadiusSDK.profileUpdate();
```

### forgotPassword()

This method triggers forgot password action and redirects to LoginRadius IDX forgot password section 

```
LoginRadiusSDK.forgotPassword({
        redirect_uri: window.location.href
    });
```

Here redirect_uri  is the return url, where the user will be redirected after forgot password action.

### getToken()

This method gets access token from the browser's local storage

```
LoginRadiusSDK.getToken();
```

### getUserProfile()

This method fetches the profile based on the access token.

```
LoginRadiusSDK.getUserProfile();
```

Demo
=====
1. Navigate to ```demo``` repository
2. Open the option.js file
3. In the options.js file, Initialize the demo with your API Key, App Name.
4. Open index.html file in browser and demo will appear.