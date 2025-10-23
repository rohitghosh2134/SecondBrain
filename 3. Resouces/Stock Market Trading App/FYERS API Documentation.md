- Introduction
- Libraries and SDKs
- Community
- General
    - Request & Response Structure
    - App Creation
    - Authentication & Login Flow - User Apps
    - Authentication & Login Flow - Third Party Apps
    - Sample Code
    - User
    - Transaction Info
    - Order Placement Guide
    - Order Placement
    - GTT Orders
    - Other Transactions
    - Margin Calculator
    - Broker Config
        - Market Status
        - Symbol Master
        - Symbol Master Json
    - EDIS
    - Postback (Webhooks)
    - Data Api
    - Web Socket
    - Order Websocket Usage Guide
    - Tick-by-Tick (TBT) Websocket Usage Guide
    - True Data V2
    - Appendix
    - Change Log

# FYERS APIS

Fyers API is a set of **REST-like APIs** that provide integration with our `in-house` trading platform with which you can build your own customized trading applications. To view the old version of docs, click [here](https://myapi.fyers.in/docs)

# [](https://myapi.fyers.in/docsv3#section/Introduction)Introduction

Fyers API is a set of **REST-like APIs** that provide integration with our in-house trading platform with which you can build your own customized trading applications. You can place fresh single or multiple orders, modify and cancel existing orders in real-time. You can also get account related information such as orderbook, tradebook, net positions, holdings, and funds.

We have ensured maximum security for our APIs which prevent unauthorised transactions. All API requests and received only over HTTPS protocol.

You can read more about when we introduced FYERS APIs [here](https://fyers.in/api/)

# [](https://myapi.fyers.in/docsv3#section/Libraries-and-SDKs)Libraries and SDKs

Certainly! To make it even easier for you to use the Fyers API in different programming languages, we have provided dedicated libraries/packages that handle the API calls for you. These libraries/packages abstract away the complexities of raw HTTP calls, allowing you to focus on integrating the API seamlessly into your applications. Below are the links to the libraries/packages.

- **[Fyers Python library](https://pypi.org/project/fyers-apiv3)** - Supports Python 3.8 to 3.12 version
- **[Fyers Node.js library](https://www.npmjs.com/package/fyers-api-v3)** - Supports Node.js 12 to 21.6.2 version
- **[Fyers Web JS library](https://www.npmjs.com/package/fyers-web-sdk-v3)** - Supports in Browser  
    
- **[Fyers C# library](https://www.nuget.org/packages/fyers-api-v3/1.0.6)** - Supports .NET 8.0.4  
    
- **[Fyers Java library](https://github.com/FyersDev/fyers-java-sdk)** - Supports Java 8  
    

**CDN Link**

|**Versions**|**Links**|
|---|---|
|1.3.0|[https://cdn.fyers.in/js/sdk/1.3.0/fyers-web-sdk-v3/index.min.js](https://cdn.fyers.in/js/sdk/1.3.0/fyers-web-sdk-v3/index.min.js)|
|1.2.1|[https://cdn.fyers.in/js/sdk/1.2.1/fyers-web-sdk-v3/index.min.js](https://cdn.fyers.in/js/sdk/1.2.1/fyers-web-sdk-v3/index.min.js)|
|1.2.0|[https://cdn.fyers.in/js/sdk/1.2.0/fyers-web-sdk-v3/index.min.js](https://cdn.fyers.in/js/sdk/1.2.0/fyers-web-sdk-v3/index.min.js)|
|1.1.0|[https://cdn.fyers.in/js/sdk/1.1.0/fyers-web-sdk-v3/index.min.js](https://cdn.fyers.in/js/sdk/1.1.0/fyers-web-sdk-v3/index.min.js)|
|1.0.0|[https://cdn.fyers.in/js/sdk/1.0.0/fyers-web-sdk-v3/index.min.js](https://cdn.fyers.in/js/sdk/1.0.0/fyers-web-sdk-v3/index.min.js)|

# [](https://myapi.fyers.in/docsv3#section/Community)Community

We have a dedicated community to discuss, share and raise feature requests on FYERS API. Our goal is to empower the AlgoTrading community in India with the most robust and easy to integrate APIs.

You can interact with us on our dedicated topic on [FYERS API](https://myapi.fyers.in/) on [FYERS Community](https://community.fyers.in/fyers-api-rha0riqv)

# [](https://myapi.fyers.in/docsv3#tag/Request-and-Response-Structure)Request & Response Structure

Everything about Request & Response Structure

## [](https://myapi.fyers.in/docsv3#tag/Request-and-Response-Structure/operation/addpet)Authorization Headers

Once the authentication is completed, you will receive an access_token. For all of the following requests, you will be required to send a combination of appId and access_token (api_id:access_token) in the HTTP Authorization header.

### Request samples

- cURL

Copy

curl -H “Authorization: api_id:access_token”
curl -H “Authorization: aaa-99:bbb”

## [](https://myapi.fyers.in/docsv3#tag/Request-and-Response-Structure/paths/~1Auth/patch)Success

## Response Attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`s`|string|“ok”|
|`code`|int|200|
|`message`|string|“”|
|`Additional key`|object / list / int / string|Each request will contain its own key based on the request|

## [](https://myapi.fyers.in/docsv3#tag/Request-and-Response-Structure/paths/~1Auth/delete)Failure

The error response attributes will contain the following

## Response Attribute

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`s`|string|“error”|
|`code`|int|Negative integer to identify the specific error|
|`message`|string|Error message to identify error|
|`HTTP Header`|int|Refer to the error codes table [View Details](https://myapi.fyers.in/docsv3#tag/Request-and-Response-Structure/paths/~1pet~1%7BpetId%7D/get)|

## [](https://myapi.fyers.in/docsv3#tag/Request-and-Response-Structure/paths/~1pet~1{petId}/get)HTTP Status Codes

The status codes contain the following

|   |   |
|---|---|
|Status Code|Meaning|
|200|Request was successful|
|400|Bad request. The request is invalid or certain other errors|
|401|Authorization error. User could not be authenticated|
|403|Permission error. User does not have the necessary permissions|
|429|Rate limit exceeded. Users have been blocked for exceeding the rate limit.|
|500|Internal server error.|

## [](https://myapi.fyers.in/docsv3#tag/Request-and-Response-Structure/paths/~1pet~1{petId}/patch)Common API Error Codes

The status codes contain the following

|   |   |
|---|---|
|Code|Description|
|-8|This error occurs when token is Expired|
|-15|This error occurs when Invalid token is provided|
|-16|This error occurs when server is unable to authenticate user token|
|-17|This error occurs when token is passed is either Invalid or Expired|
|-50|This error occurs when one or more invalid parameters are passed. The message field in the API response will include details about the specific invalid inputs.|
|-51|This error occurs when invalid Order ID is passed while fetching Orders or Order Modification|
|-53|This error occurs when invalid position ID is passed|
|-99|This error occurs when order placement get rejected with rejection message in the API response|
|-300|This error occurs when invalid symbol provided|
|-352|This error occurs when invalid App ID is provided|
|-352|This error occurs in exit position API, if no position available to exit|
|-429|This error occurs when the API rate limit is exceeded, either per second, minute, or day.|
|400|This error occurs in multi leg order placement when invalid input passed|

## [](https://myapi.fyers.in/docsv3#tag/Request-and-Response-Structure/paths/~1pet~1{petId}/post)Rate Limit

|   |   |
|---|---|
|Timeframe|Rate Limit|
|Per Second|10|
|Per Minute|200|
|Per Day|100000|

## [](https://myapi.fyers.in/docsv3#tag/Request-and-Response-Structure/paths/~1pet~1{petId}/delete)Permission Templates

You can provide different app permissions for each application at the time of creation.

|   |   |   |   |   |
|---|---|---|---|---|
|Permission Template|Basic|Transactions Info|Order Placement|Market Data|
|List of activities allowed|1. Profile Details<br>2. Logout App<br>3. Logout|1. Basic Included<br>2. Orders<br>3. Positions<br>4. Trades<br>5. Holdings<br>6. Funds<br>7. Market Status|1. Transactions Info Included<br>2. Order Placement<br>3. Order Modification<br>4. Order Cancellation<br>5. Exit Positions<br>6. Convert Positions|1. Historical data<br>2. Market Depth<br>3. Quotes|

## [](https://myapi.fyers.in/docsv3#tag/Request-and-Response-Structure/paths/~1pet~1{petId}/put)User blocking

The user will be blocked for the rest of the day if the per minute rate limit is exceeded more than 3 times in the day.

# [](https://myapi.fyers.in/docsv3#tag/App-Creation)App Creation

## [](https://myapi.fyers.in/docsv3#tag/App-Creation/Individual-Apps)Individual Apps

These are apps which are created for your own personal usage. These apps can be used only by the creator of the app and no other client can login and make use of this particular app.  
To create an app, you need to follow the following steps:-

1. Login to API [Dashboard](https://myapi.fyers.in/dashboard)
2. Click on Create App
3. Provide the following details
    - App Icon
    - App Name
    - Redirect URL
    - Description (Optional)
    - App Permissions - Refer Permissions Template

![](https://assets.fyers.in/myapi-dashboard/docs/api_docs_example.png)

## [](https://myapi.fyers.in/docsv3#tag/App-Creation/Third-Party-Apps)Third Party Apps

These apps are used by platform providers which would allow end users to login to the app and make use of the functionality. These apps are created by third party application providers to enable FYERS clients to use their applications.  
To create a common app, you can get in touch with us at [api-support@fyers.in](mailto:api-support@fyers.in).

## [](https://myapi.fyers.in/docsv3#tag/App-Creation/Redirect-URI)Redirect URI

The user will be redirected to the redirect uri after successfully logging in using the FYERS credentials. The redirect uri should be in your control as the auth token is sensitive information.

# [](https://myapi.fyers.in/docsv3#tag/Authentication-and-Login-Flow-User-Apps)Authentication & Login Flow - User Apps

## [](https://myapi.fyers.in/docsv3#tag/Authentication-and-Login-Flow-User-Apps/paths/~1Authentication%20&%20Login%20Flow%20-%20User%20Apps/post)Authentication Steps

The login flow is as follows:

1. Navigate to the Login API endpoint
2. After successful login, user is redirected to the redirect uri with the auth_code
3. POST the auth_code and appIdHash (SHA-256 of api_id + app_secret) to Validate Authcode API endpoint
4. Obtain the access_token use that for all the subsequent requests

## [](https://myapi.fyers.in/docsv3#tag/Authentication-and-Login-Flow-User-Apps/paths/~1Authentication%20&%20Login%20Flow%20-%20User%20Apps/patch)Request Parameters for Step 1

## Request Attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`client_id`|string|This is the app_id which you have received after creating the app.  <br>Eg: “qwerty-100”|
|`redirect_uri`|string|This is where the user will be redirected after successful login.  <br>Eg: [https://trade.fyers.in/api-login/redirect-uri/index.html](https://trade.fyers.in/api-login/redirect-uri/index.html)  <br>**This should be the same as what was provided at the time of app creation**|
|`response_type`|string|This value must always be “code”|
|`state`|string|You send a random value. The same value will be returned after successful login to the redirect uri.  <br>Eg: “abcdefg”|

## Response Attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`s`|string|ok / error|
|`code`|int|This is the code to identify specific responses|
|`message`|string|This is the message to identify the specific error responses|
|`auth_code`|string|String value which will be used to generate the access_token|
|`state`|string|This value is returned as is from the first request|

### Request samples

- cURL
- Python
- Node
- Web modular API
- C#
- Java

Copy

curl --location --request GET 'https://api-t1.fyers.in/api/v3/generate-authcode?client_id=SPXXXXE7-100&redirect_uri=https://trade.fyers.in/api-login/redirect-uri/index.html&response_type=code&state=sample_state'

## [](https://myapi.fyers.in/docsv3#tag/Authentication-and-Login-Flow-User-Apps/paths/~1Authentication%20&%20Login%20Flow%20-%20User%20Apps/get)Request Parameters for Step 2

## Request Attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`grant_type`|string|This value must always be “authorization_code|
|`appIdHash`|string|SHA-256 of api_id + app_secret  <br>Eg: SHA-256 of app_id:app_secret is  <br>7c7120d2b5004f8de22d8dc2da0453b4d7e6211e37a4108b83712  <br>66ecff00498  <br>You can use this [online tool](https://emn178.github.io/online-tools/sha256.html) for reference|
|`code`|string|This is the auth_code which is received from the first step|

## Response Attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`s`|string|ok / error|
|`code`|int|This is the code to identify specific responses|
|`message`|string|This is the message to identify the specific error responses|
|`access_token`|string|This value will be used for all the subsequent requests.|

### Request samples

- cURL
- Python
- Node
- Web modular API
- C#
- Java

Copy

curl --location --request POST 'https://api-t1.fyers.in/api/v3/validate-authcode' \
--header 'Content-Type: application/json' \
--data-raw '{
    "grant_type":"authorization_code",  
    "appIdHash":"c3efb1075ef2332b3a4ec7d44b0f05c1********************",
    "code":"eyJ0eXAi*******.eyJpc3MiOiJhcGkubG9********.r_65Awa1kGdsNTAgD******"
}'

----------------------------------------------------------------------------------
Sample Success Response               
----------------------------------------------------------------------------------          

{
  's': 'ok',
  'code': 200,
  'message': '',
  'access_token': 'eyJ0eXAiOi***.eyJpc3MiOiJh***.HrSubihiFKXOpUOj_7***',
  'refresh_token': 'eyJ0eXAiO***.eyJpc3MiOiJh***.67mXADDLrrleuEH_EE***'
}

## [](https://myapi.fyers.in/docsv3#tag/Authentication-and-Login-Flow-User-Apps/paths/~1Authentication%20&%20Login%20Flow%20-%20User%20Apps/delete)Refresh Token

When we validate the auth code to generate the access token, a refresh token is also sent in the response.  
  
The refresh token has a validity of 15 days. A new access token can be generated using the refresh token as long as the refresh token is valid.  
  
The following parameters must be passed in the body for the POST request

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`grant_type`|string|The grant_type parameter must be set to “refresh_token”.|
|`appIdHash`|string|SHA-256 of api_id + app_secret. Eg: SHA-256 of app_id:app_secret is c7120d2b5004f8de22d8dc2da0453b4d7e6211e37a4108b8371266ecff00498. You can use this online tool for reference ([https://emn178.github.io/online-tools/sha256.html](https://emn178.github.io/online-tools/sha256.html))|
|`refresh_token`|string|The refresh token previously issued to the client from the validate auth code API|
|`pin`|string|The user's pin|

### Request samples

- cURL

Copy

curl --location --request POST 'https://api-t1.fyers.in/api/v3/validate-refresh-token' \
--header 'Content-Type: application/json' \
--data-raw '{
  "grant_type": "refresh_token",
  "appIdHash": "c3efb1075ef2332b3a4ec7d44b0f05c1********************",
  "refresh_token": "eyJ0eXAiOiJKV1***.eyJpc3MiOiJhcGkuZn***.5_Qpnd1nQXBw1T_wNJNFF***",
  "pin": "****"
}'

----------------------------------------------------------------------------------
Sample Success Response 
----------------------------------------------------------------------------------

{
    "s": "ok",
    "code": 200,
    "message": "",
    "access_token": "eyJ0eXAiOiJK***.eyJpc3MiOiJhcGkuZnllcnM***.IzcuRxg4tnXiULCx3***"
}

## [](https://myapi.fyers.in/docsv3#tag/Authentication-and-Login-Flow-User-Apps/paths/~1Authentication%20&%20Login%20Flow%20-%20User%20Apps/put)Best Practices

These are the recommended best practises that you should follow while using the APIs

1. Never share your app_secret with anyone
2. Never share your access_token with anyone
3. Do not provide trading permissions unless you want to use the app to place orders
4. Provide a redirect_uri which is in your control rather than a public endpoint such as google.com
5. You should send a random value in the state parameter and verify whether the same value has been returned to you

# [](https://myapi.fyers.in/docsv3#tag/Authentication-and-Login-Flow-Third-Party-Apps)Authentication & Login Flow - Third Party Apps

OAuth2 is authentication flow for Third Party Apps

## [](https://myapi.fyers.in/docsv3#tag/Authentication-and-Login-Flow-Third-Party-Apps/paths/~1ThirdParty/post)OAuth2 - Auth Flow

This is a simple OAuth 2 Authentication Flows.

- This is recommended for applications which have a backend server which can authenticate the second step
- This is **not recommended** for Single Page Applications (SPA)
- **Diagram**  
    

- ### Request Parameters for Step 1
    
    You need to navigate the user to the FYERS login url with the correct get parameters
    
    ## Request Attributes
    
    |**Attribute**|**Data Type**|**Description**|
    |---|---|---|
    |`client_id`|string|This is the app_id which you have received after creating the app.  <br>Eg: “qwerty-102”|
    |`redirect_uri`|string|This is where the user will be redirected after successful login.  <br>Eg:  <br>[https://trade.fyers.in/api-login/redirect-uri/index.html](https://trade.fyers.in/api-login/redirect-uri/index.html)  <br>**This should be the same as what was provided at the time of app creation**|
    |`response_type`|string|This value must always be “code”|
    |`state`|string|You send a random value. The same value will be returned after successful login to the redirect uri.  <br>Eg: “abcdefg”|
    
    ## Response Attributes
    
    |**Attribute**|**Data Type**|**Description**|
    |---|---|---|
    |`s`|string|ok / error|
    |`code`|int|This is the code to identify specific responses|
    |`message`|string|This is the message to identify the specific error responses|
    |`auth_code`|string|String value which will be used to generate the access_token|
    |`state`|string|This value is returned as is from the first request|
    
- ### Request Parameters for Step 2
    
    ## Request Attributes
    
    |**Attribute**|**Data Type**|**Description**|
    |---|---|---|
    |`grant_type`|string|This value must always be “authorization_code”|
    |`appIdHash`|string|SHA-256 of api_id + app_secret  <br>Eg: SHA-256 of app_id:app_secret is  <br>c7120d2b5004f8de22d8dc2da0453b4d7e6211e37a4108b8371266ecff00498  <br>You can use this [online tool](https://emn178.github.io/online-tools/sha256.html) for reference|
    |`code`|string|This is the auth_code which is received from the first step|
    
    ## Response Attributes
    
    |**Attribute**|**Data Type**|**Description**|
    |---|---|---|
    |`s`|string|ok / error|
    |`code`|int|This is the code to identify specific responses|
    |`message`|string|This is the message to identify the specific error responses|
    |`access_token`|string|This value will be used for all the subsequent requests.|
    

### Request samples

- cURL

Copy

curl -H "Content-Type: application/json" -X POST -d 
   '{
         "grant_type":"authorization_code","appIdHash":"d8f152a3c455add2bd636a2ec6ff893394c8cc4e84d439d95951510b032500e3","code":"eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJhcGkubG9naW4uZnllcnMuaW4iLCJpYXQiOjE2MDEyOTExNDIsImV4cCI6MTYwMTI5MTQ0MiwibmJmIjoxNjAxMjkxMTQyLCJhdWQiOlsieDoyIiwieDoxIiwieDowIl0sInN1YiI6ImF1dGhfY29kZSIsImRpc3BsYXlfbmFtZSI6IkRQMDA0MDQiLCJub25jZSI6IiIsImFwcF9pZCI6IklESTdYTkpDWU0iLCJ1dWlkIjoiOWQ4N2MxZjk5MWEzNDI1YWIxYWJjYTg5ODgxYTcyZjAiLCJpcEFkZHIiOiIxMDMuNTcuODIuMTA4Iiwic2NvcGUiOiIifQ.ypHzr332QEWv3tidrdtqU2k42Z4EyqT-nTBIZAhpKI4"
   }' https://api-t1.fyers.in/api/v3/validate-authcode 

 ------------------------------------------------------------------------------------------------------------------------------------------
 Sample Success Response 
 ------------------------------------------------------------------------------------------------------------------------------------------
           
 {
   "s": "ok",
   "code": 200,
   "message": "",
   "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJhcGkuZnllcnMuaW4iLCJpYXQiOjE2MDEyOTExNjAsImV4cCI6MTYwMTMzOTQwMCwibmJmIjoxNjAxMjkxMTYwLCJhdWQiOlsieDoyIiwieDoxIiwieDowIl0sInN1YiI6ImFjY2Vzc190b2tlbiIsImF0X2hhc2giOiJnQUFBQUFCZmNjT1l6WVdtVnpvNldNVUJ1OTBnV29GbkJKUWViS2p2LUg4NDY5dEV4cWdWNWNmWVdJQ1Q0eWFTTUJiN0hhVmJBUFJESzgtbzhYQUZpX2w4OERzVXdudllWTjc2R25BYV9HZEFvdTc1LVZ1c29Rbz0iLCJkaXNwbGF5X25hbWUiOiJQSVlVU0ggUkFKRU5EUkEgS0FQU0UiLCJmeV9pZCI6IkRQMDA0MDQiLCJhcHBUeXBlIjoxMDJ9.5FnygsaTu9ySRk1b2VYhYtjH1L9wQ9rtX0F1vLvf5x0"
 }

## [](https://myapi.fyers.in/docsv3#tag/Authentication-and-Login-Flow-Third-Party-Apps/paths/~1ThirdParty/put)Best Practices

These are the recommended best practises that you should follow while using the APIs

- Never share your app_secret with anyone
- Never share your access_token with anyone
- Do not provide trading permissions unless you want to use the app to place orders
- Provide a redirect_uri which is in your control rather than a public endpoint such as google.com
- You should send a random value in the state parameter and verify whether the same value has been returned to you
- Do not store the app_secret in the front end. It should be securely kept without exposing it to third parties.

# [](https://myapi.fyers.in/docsv3#tag/Sample-Code)Sample Code

## [](https://myapi.fyers.in/docsv3#tag/Sample-Code/Postman-Collection)Postman Collection

We have created an extensive Postman collection which will make it easier for implementation. Kindly import the postman_collection & postman_environment_variables

- Download and import the postman collection from [here](https://github.com/FyersDev/fyers-api-sample-code/blob/sample_v3/v3/Postman%20V3/FYERS%20API%20V3.postman_collection.json)
- Download and import the postman environment variables from [here](https://github.com/FyersDev/fyers-api-sample-code/blob/sample_v3/v3/Postman%20V3/FYERS%20API%20V3.postman_environment.json)
- You can check the sample Script to get started with from [here](https://github.com/FyersDev/fyers-api-sample-code/tree/sample_v2/My%20API%20Sample%20Script\(GET%20STARTED\))
- We have provided dummy data in the environment variables. Kindly update the correct values after you import it.

# [](https://myapi.fyers.in/docsv3#tag/User)User

## [](https://myapi.fyers.in/docsv3#tag/User/paths/~1User/delete)FyersModel Class (Python SDK)

When initialized, it requires parameters such as client_id and access_token for authentication.This class supports synchronous execution by default (is_async=False). Additionally, it enables logging functionality, allowing users to specify a log path (log_path) where logs will be stored. By default, the logging level is set to 'error', but users have the option to set it to 'debug' for more detailed logging information.

## Arguments in FyersModel Class

|**Arguments**|**Data Type**|**Description**|
|---|---|---|
|`client_id`|string|For authentication|
|`access_token`|string|For authentication|
|`isAsync(optional)`|boolean|Default value is False for synchronous flow, for asynchronous set it True|
|`log_path(optional)`|string|Specify the file path where you want to store the logs|
|`log_level(optional)`|string|By default, the logging level is set to 'ERROR', level can be set 'DEBUG' for more detailed logs.|

## [](https://myapi.fyers.in/docsv3#tag/User/paths/~1User/post)Profile

This allows you to fetch basic details of the client.

## Response Attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`name`|string|Name of the client|
|`display_name`|string|Display name, if any, provided by the client|
|`fy_id`|string|The client id of the fyers user|
|`image`|string|URL link to the user’s profile picture, if any.|
|`email_id`|string|Email address of the client|
|`pan`|string|PAN of the client|
|`pin_change_date`|string|Date when last PIN was updated|
|`pwd_change_date`|string|Date when last password was updated|
|`mobile_number`|string|Registered mobile number|
|`totp`|boolean|Status of TOTP|
|`pwd_to_expire`|int|Number of days until the current password expires|
|`ddpi_enabled`|boolean|Status of DDPI|
|`mtf_enabled`|boolean|Status of MTF|

### Request samples

- cURL
- Python
- Node
- Web modular API
- C#
- Java

Copy

Curl Request Method
curl -H "Authorization:app_id:access_token" https://api-t1.fyers.in/api/v3/profile

----------------------------------------------------------------------------------------------------------------
Sample Response
----------------------------------------------------------------------------------------------------------------
{
   "s": "ok",
   "code": 200,
   "message": "",
   "data": {
             "name": "XASHXX G H",
             "image": "https://fyers-user-details.s3.amazonaws.com/image/FK6107548224?X-Amz-Algorithm=AWS4-HMAC",
             "display_name":"Y2K",
             "email_id":"xashxx.ghang@gmail.com",
             "PAN": "EXXXXXXXXE",
             "fy_id": "FX0011",
             "pin_change_date": "19-08-2020 14:58:41",
             "mobile_number": "xxxxxxxxxx",
             "totp": true,
             "pwd_change_date": "19-08-2020 14:58:41",
             "pwd_to_expire": 42,
             "ddpi_enabled": false,
             "mtf_enabled": false
            }
  }

## [](https://myapi.fyers.in/docsv3#tag/User/paths/~1User/put)Funds

Shows the balance available for the user for capital as well as the commodity market.

## Response Attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`id`|int|Unique identity for particular fund|
|`title`|string|Each title represents a heading of the ledger|
|`equityAmount`|float|The amount in the capital ledger for the above-mentioned title|
|`commodityAmount`|float|The amount in the commodity ledger for the above-mentioned title|

### Request samples

- cURL
- Python
- Node
- Web modular API
- C#
- Java

Copy

Curl Request Method
curl -H "Authorization: app_id:access_token" https://api-t1.fyers.in/api/v3/funds

----------------------------------------------------------------------------------------------------------------
 Sample Response
----------------------------------------------------------------------------------------------------------------
 {
    "code":200,
    "message":"",
    "s":"ok",
    "fund_limit":[
        {
          "id":1,
          "title":"Total Balance",
          "equityAmount":58.150000000000006,
          "commodityAmount":0
        },
        {
          "id":2,
          "title":"Utilized Amount",
          "equityAmount":0.3,
          "commodityAmount":0
        },
        {
          "id":3,
          "title":"Clear Balance",
          "equityAmount":58.150000000000006,
          "commodityAmount":0
        },
        {
          "id":4,
          "title":"Realized Profit and Loss",
          "equityAmount":-0.3,
          "commodityAmount":0
        },
        {
          "id":5,
          "title":"Collaterals",
          "equityAmount":0,
          "commodityAmount":0
        },
        {
          "id":6,
          "title":"Fund Transfer",
          "equityAmount":0,
          "commodityAmount":0
        },
        {
          "id":7,
          "title":"Receivables",
          "equityAmount":0,
          "commodityAmount":0
        },
        {
          "id":8,
          "title":"Adhoc Limit",
          "equityAmount":0,
          "commodityAmount":0
        },
        {
          "id":9,
          "title":"Limit at start of the day",
          "equityAmount":58.45,
          "commodityAmount":0
        },
        {
          "id":10,
          "title":"Available Balance",
          "equityAmount":58.150000000000006,
          "commodityAmount":0
        }
    ]
  }

## [](https://myapi.fyers.in/docsv3#tag/User/paths/~1User/get)Holdings

Fetches the equity and mutual fund holdings which the user has in this demat account. This will include T1 and demat holdings.

## Request Attributes - For each holding

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`symbol`|string|Eg: NSE:RCOM-EQ|
|`holdingType`|string|Identify the type of holding  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Holding-Types)|
|`quantity`|int|The quantity of the symbol which the user has at the beginning of the day|
|`remainingQuantity`|int|This reflects the quantity - the quantity sold during the day|
|`pl`|float|Profit and loss made|
|`costPrice`|float|The original buy price of the holding|
|`marketVal`|float|The Market value of the current holding|
|`ltp`|float|LTP is the price from which the next sale of the stocks happens|
|`id`|int|The unique value for each holding|
|`fytoken`|string|Fytoken is a unique identifier for every symbol.  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Fytoken)|
|`exchange`|int|The exchange in which order is placed.  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Exchanges)|
|`segment`|int|The segment in which the holding is taken.  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Segments)|
|`isin`|string|Unique ISIN provided by exchange for each symbol|
|`qty_t1`|int|Quantity t+1 day|
|`remainingPledgeQuantity`|int|Remaining Pledged quantity|
|`collateralQuantity`|int|Pledged quantity|

## Response Attributes - Overall holdings

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`count_total`|int|Total number of holdings present|
|`total_investment`|float|Invested amount for the current holdings|
|`total_current_value`|float|The present value of the holdings|
|`total_pl`|float|Total profit and loss made|
|`pnl_perc`|float|Percentage value of the total pnl|

### Request samples

- cURL
- Python
- Node
- Web modular API
- C#
- Java

Copy

Curl Request Method
curl -H "Authorization: app_id:access_token" https://api-t1.fyers.in/api/v3/holdings

--------------------------------------------------------------------------------------------------------------------------------
 Sample Response
--------------------------------------------------------------------------------------------------------------------------------
 {
   "s": "ok",
   "code": 200,
   "message": "",
   "holdings":
               [{
                 "holdingType":"HLD",
                 "quantity":1,
                 "costPrice":1.55,
                 "marketVal": 3.75,
                 "remainingQuantity":1,
                 "pl":2.2,
                 "ltp":3.75,
                 "id":1,
                 "fyToken":101000000011460,
                 "exchange":10,
                 "symbol":"NSE:JPASSOCIAT-EQ",
                 "segment": 10,
                 "isin": "INE669E01016",
                 "qty_t1": 1,
                 "remainingPledgeQuantity": -1,
                 "collateralQuantity": 0,
               },
               {
                 "holdingType":"HLD",
                 "quantity":1,
                 "costPrice":192.6,
                 "marketVal": 149.70,
                 "remainingQuantity":1,
                 "pl":-42.9,
                 "ltp":149.7,
                 "id":2,
                 "fyToken":10100000003812,
                 "exchange":10,
                 "symbol":"NSE:ZEEL-EQ",
                 "segment": 10,
                 "isin": "INE669E01016",
                 "qty_t1": 1,
                 "remainingPledgeQuantity": -1,
                 "collateralQuantity": 0,
               }],
     "overall":
               {
                 "count_total":2,
                 "total_investment":194.15,
                 "total_current_value":153.45,
                 "total_pl": -40.7,
                 "pnl_perc":-10.48,
               }    
 }

## [](https://myapi.fyers.in/docsv3#tag/User/paths/~1User/patch)Logout

This invalidates the access token, revoking it only for the specific app without affecting other active apps or web and mobile sessions.

### Request samples

- cURL
- Python
- Node
- Web Modular API
- Java

Copy

Curl Request Method
curl -H "Authorization: app_id:access_token" POST 'https://api-t1.fyers.in/api/v3/logout'

--------------------------------------------------------------------------------------------------------------------------------
Sample Response
--------------------------------------------------------------------------------------------------------------------------------
{
  "s": "ok",
  "code": 200,
  "message": "you are successfully logged out",
}

# [](https://myapi.fyers.in/docsv3#tag/Transaction-Info)Transaction Info

## [](https://myapi.fyers.in/docsv3#tag/Transaction-Info/paths/~1Transaction%20Info/post)Orders

Fetches all the orders placed by the user across all platforms and exchanges in the current trading day.

## Response attributes - For each order

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`id`|string|The unique order id assigned for each order|
|`exchOrdId`|string|The order id provided by the exchange|
|`symbol`|string|The symbol for which order is placed|
|`qty`|int|The original order qty|
|`remainingQuantity`|int|The remaining qty|
|`filledQty`|int|The filled qty after partial trades|
|`status`|int|- 1 => Canceled<br>- 2 => Traded / Filled<br>- 3 => (Not used currently)<br>- 4 => Transit<br>- 5 => Rejected<br>- 6 => Pending<br>- 7 => Expired<br>- [View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Order-Status)|
|`slNo`|int|This is used to sort the orders based on the time|
|`message`|string|The error messages are shown here|
|`segment`|int|- 10 => E (Equity)<br>- 11 => D (F&O)<br>- 12 => C (Currency)<br>- 20 => M (Commodity)<br>- [View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Segments)|
|`limitPrice`|float|The limit price for the order|
|`stopPrice`|float|The limit price for the order|
|`productType`|string|The product type|
|`type`|int|- 1 => Limit Order<br>- 2 => Market Order<br>- 3 => Stop Order (SL-M)<br>- 4 => Stoplimit Order (SL-L)|
|`side`|int|- 1 => Buy<br>- -1 => Sell<br>- [View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Order-Sides)|
|`disclosedQty`|int|Disclosed quantity|
|`orderValidity`|string|- DAY<br>- IOC|
|`orderDateTime`|string|The order time as per DD-MMM-YYYY hh:mm:ss in IST|
|`parentId`|string|The parent order id will be provided only for applicable orders..  <br>Eg: BO Leg 2 & 3 and CO Leg 2|
|`tradedPrice`|float|The average traded price for the order|
|`source`|string|Source from where the order was placed.  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Order-Sources)|
|`fytoken`|string|Fytoken is a unique identifier for every symbol.  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Fytoken)|
|`offlineOrder`|boolean|- False => When market is open<br>- True => When placing AMO order|
|`pan`|string|PAN of the client|
|`clientId`|string|The client id of the fyers user|
|`exchange`|int|The exchange in which order is placed  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Exchanges)|
|`instrument`|int|Exchange instrument type  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Instrument-Types)|
|`discloseQty`|int|Disclosed quantity|
|`orderTag`|string|ordertag provided when placing the order  <br>**Note**: `1:` will be concatenated at the start of tag provided by user.  <br>`2:` will be concatenated at the start of tag generated internally by Fyers.  <br>Default value if tag not provided when order is placed is `2:Untagged`|

### Request samples

- cURL
- Python
- Node
- Web modular API
- C#
- Java

Copy

Curl Request Method
curl -H "Authorization: app_id:access_token" https://api-t1.fyers.in/api/v3/orders

---------------------------------------------------------------------------------------------------------------------------------------------
 Sample Success Response 
---------------------------------------------------------------------------------------------------------------------------------------------
Response structure:
{
  "s": "ok",
  "code": 200,
  "message": "",
  "orderBook": [{
      "clientId": "X******",
      "id": "23030900015105",
      "exchOrdId": "1100000001089341",
      "qty": 1,
      "remainingQuantity": 0,
      "filledQty": 1,
      "discloseQty": 0,
      "limitPrice": 6.95,
      "stopPrice": 0,
      "tradedPrice": 6.95,
      "type": 1,
      "fyToken": "101000000014366",
      "exchange": 10,
      "segment": 10,
      "symbol": "NSE:IDEA-EQ",
      "instrument": 0,
      "message": "",
      "offlineOrder": False,
      "orderDateTime": "09-Mar-2023 09:34:38",
      "orderValidity": "DAY",
      "pan": "",
      "productType": "CNC",
      "side": -1,
      "status": 2,
      "source": "W",
      "ex_sym": "IDEA",
      "description": "VODAFONE IDEA LIMITED",
      "ch": -0.1,
      "chp": -1.44,
      "lp": 6.85,
      "slNo": 1,
      "dqQtyRem": 0,
      "orderNumStatus": "23030900015105:2",
      "disclosedQty": 0,
      "orderTag": "1:Ordertag"
  }]
}

## [](https://myapi.fyers.in/docsv3#tag/Transaction-Info/paths/~1Transaction%20Info/put)Order Filter By Order Id

You can query for a particular order id by passing the id in the get parameters

### Request samples

- cURL
- Python
- Node
- Web modular API
- C#
- Java

Copy

Curl Request Method
curl -H "Authorization:app_id:access_token"  https://api-t1.fyers.in/api/v3/orders?id=sample_order_id

-----------------------------------------------------------------
Sample Success Response
-----------------------------------------------------------------
{
  "s": "ok",
  "code": 200,
  "message": "",
  "orderBook": [{
      "clientId": "X******",
      "id": "23030900015105",
      "exchOrdId": "1100000001089341",
      "qty": 1,
      "remainingQuantity": 0,
      "filledQty": 1,
      "discloseQty": 0,
      "limitPrice": 6.95,
      "stopPrice": 0,
      "tradedPrice": 6.95,
      "type": 1,
      "fyToken": "101000000014366",
      "exchange": 10,
      "segment": 10,
      "symbol": "NSE:IDEA-EQ",
      "instrument": 0,
      "message": "",
      "offlineOrder": False,
      "orderDateTime": "09-Mar-2023 09:34:38",
      "orderValidity": "DAY",
      "pan": "",
      "productType": "CNC",
      "side": -1,
      "status": 2,
      "source": "W",
      "ex_sym": "IDEA",
      "description": "VODAFONE IDEA LIMITED",
      "ch": -0.1,
      "chp": -1.44,
      "lp": 6.85,
      "slNo": 1,
      "dqQtyRem": 0,
      "orderNumStatus": "23030900015105:2",
      "disclosedQty": 0,
      "orderTag": "1:Ordertag"
  }]
}

## [](https://myapi.fyers.in/docsv3#tag/Transaction-Info/paths/~1Transaction%20Info/head)Order Filter By Order tag

You can query for a particular orderTag by passing the orderTag in the get parameters

### Request samples

- cURL

Copy

Curl Request Method
curl -H "Authorization:app_id:access_token"  https://api-t1.fyers.in/api/v3/orders??order_tag=1:Ordertag

-----------------------------------------------------------------
Sample Success Response
-----------------------------------------------------------------
{
  "s": "ok",
  "code": 200,
  "message": "",
  "orderBook": [{
      "clientId": "X******",
      "id": "23030900015105",
      "exchOrdId": "1100000001089341",
      "qty": 1,
      "remainingQuantity": 0,
      "filledQty": 1,
      "discloseQty": 0,
      "limitPrice": 6.95,
      "stopPrice": 0,
      "tradedPrice": 6.95,
      "type": 1,
      "fyToken": "101000000014366",
      "exchange": 10,
      "segment": 10,
      "symbol": "NSE:IDEA-EQ",
      "instrument": 0,
      "message": "",
      "offlineOrder": False,
      "orderDateTime": "09-Mar-2023 09:34:38",
      "orderValidity": "DAY",
      "pan": "",
      "productType": "CNC",
      "side": -1,
      "status": 2,
      "source": "W",
      "ex_sym": "IDEA",
      "description": "VODAFONE IDEA LIMITED",
      "ch": -0.1,
      "chp": -1.44,
      "lp": 6.85,
      "slNo": 1,
      "dqQtyRem": 0,
      "orderNumStatus": "23030900015105:2",
      "disclosedQty": 0,
      "orderTag": "1:Ordertag"
  }]
}

## [](https://myapi.fyers.in/docsv3#tag/Transaction-Info/paths/~1Transaction%20Info/patch)Positions

Fetches the current open and closed positions for the current trading day. Note that previous trading day’s closed positions will not be shown here.

## Response attributes - For each position

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`symbol`|string|Eg: NSE:SBIN-EQ|
|`id`|string|The unique value for each position|
|`buyAvg`|float|Average buy price|
|`buyQty`|int|Total buy qty|
|`sellAvg`|float|Average sell price|
|`sellQty`|int|Total sell qty|
|`netAvg`|float|netAvg|
|`netQty`|int|Net qty|
|`side`|int|The side shows whether the position is long / short  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Position-Sides)|
|`qty`|int|Absolute value of net qty|
|`productType`|string|The product type of the position  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Product-Types.)|
|`realized_profit`|float|The realized p&l of the position|
|`pl`|float|The total p&l of the position|
|`crossCurrency`|string|Y => It is cross currency position  <br>N => It is not a cross currency position|
|`rbiRefRate`|float|Incase of cross currency position, the rbi reference rate will be required to calculate the p&l|
|`qtyMulti_com`|float|Incase of commodity positions, this multiplier is required for p&l calculation|
|`segment`|int|The segment in which the position is taken.  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Segments)|
|`exchange`|int|The exchange in which the position is taken.  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Exchanges)|
|`slNo`|int|This is used for sorting of positions|
|`ltp`|float|LTP is the price from which the next sale of the stocks happens|
|`fytoken`|string|Fytoken is a unique identifier for every symbol.  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Fytoken)|
|`cfBuyQty`|int|Carry forward buy quantity|
|`cfSellQty`|int|Carry forward sell quantity|
|`dayBuyQty`|int|Day forward buy quantity|
|`daySellQty`|int|Day forward sell quantity|
|`exchange`|int|The exchange in which order is placed  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Exchanges)|

## Response attributes - Overall Positions

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`count_total`|int|Total number of positions present|
|`count_open`|int|Total number of positions opened|
|`pl_total`|float|Total profit and losses|
|`pl_realized`|float|Profit and losses when the owned product is sold|
|`pl_unrealized`|float|Profit and loses when the product is owned , but is not sold|

### Request samples

- cURL
- Python
- Node
- Web modular API
- C#
- Java

Copy

Curl Request Method
curl -H "Authorization: app_id:access_token" https://api-t1.fyers.in/api/v3/positions

---------------------------------------------------------------------------
Sample Success Response
--------------------------------------------------------------------------
{
    "s": "ok",
    "code": 200,
    "message": "",
    "netPositions":
                [{
                  "netQty":1,
                  "qty":1,
                  "avgPrice":72256.0,
                  "netAvg": 71856.0,
                  "side":1,
                  "productType":"MARGIN",
                  "realized_profit":400.0,
                  "unrealized_profit":461.0,
                  "pl":861.0,
                  "ltp":72717.0,
                  "buyQty":2,
                  "buyAvg":72256.0,
                  "buyVal":144512.0,
                  "sellQty":1,
                  "sellAvg":72656.0,
                  "sellVal":72656.0,
                  "slNo":0,
                  "fyToken":"1120200831217406",
                  "crossCurrency":"N",
                  "rbiRefRate":1.0,
                  "qtyMulti_com":1.0,
                  "segment":20,
                  "symbol":"MCX:SILVERMIC20AUGFUT",
                  "id":"MCX:SILVERMIC20AUGFUT-MARGIN",
                  "cfBuyQty": 0,
                  "cfSellQty": 0,
                  "dayBuyQty": 0,
                  "daySellQty": 1,
                  "exchange": 10,
                }],
    "overall":
                {
                  "count_total":1,
                  "count_open":1,
                  "pl_total":861.0,
                  "pl_realized":400.0,
                  "pl_unrealized":461.0
                }            
 }

## [](https://myapi.fyers.in/docsv3#tag/Transaction-Info/paths/~1Transaction%20Info/get)Trades

Fetches all the trades for the current day across all platforms and exchanges in the current trading day.

## Response attributes - For each trade

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`symbol`|string|Eg: NSE:SBIN-EQ|
|`row`|int|The unique value to sort the trades|
|`orderDateTime`|string|The time when the trade occured in “DD-MM-YYYY hh:mm:ss” format in IST|
|`orderNumber`|string|The order id for which the trade occurred|
|`tradeNumber`|string|The trade number generated by the exchange|
|`tradePrice`|float|The traded price|
|`tradeValue`|float|The total traded value|
|`tradedQty`|int|The total traded qty|
|`side`|int|- 1 => Buy<br>- -1 => Sell<br>- [View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Order-Sides)|
|`productType`|string|The product in which the order was placed  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Product-Types.)|
|`exchangeOrderNo`|string|The order number provided by the exchange|
|`segment`|int|The segment in which order is placed  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Segments)|
|`exchange`|int|The exchange in which order is placed  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Exchanges)|
|`fyToken`|string|Fytoken is a unique identifier for every symbol.|
|`orderTag`|string|ordertag provided when placing the order  <br>**Note**: `1:` will be concatenated at the start of tag provided by user.  <br>`2:` will be concatenated at the start of tag generated internally by Fyers.  <br>Default value if tag not provided when order is placed is `1:Untagged`|

### Request samples

- cURL
- Python
- Node
- Web modular API
- C#
- Java

Copy

Curl Request Method
curl -H "Authorization: app_id:access_token" https://api-t1.fyers.in/api/v3/tradebook

-------------------------------------------------------------------
Sample Success Response
-------------------------------------------------------------------
{
  "s": "ok",
  "code": 200,
  "message": "",
  "tradeBook":
              [{
                "clientId":"FXXXXX",
                "orderDateTime":"07-Aug-2020 13:51:12",
                "orderNumber":"120080789075",
                "exchangeOrderNo": "1200000009204725",
                "exchange":10,
                "side":1,
                "segment":10,
                "orderType":2,
                "fyToken":"101000000010666",
                "productType":"CNC",
                "tradedQty":10,
                "tradePrice":32.7,
                "tradeValue":327.0,
                "tradeNumber":"52605023",
                "row":52605023,
                "symbol":"NSE:PNB-EQ",
                "orderTag": "1:Ordertag"
              },
              {
                "clientId":"FXXXXX",
                "orderDateTime":"07-Aug-2020 13:48:12",
                "orderNumber":"120080789139",
                "exchangeOrderNo": "1000000012031528",
                "exchange":10,
                "side":1,
                "segment":10,
                "orderType":2,
                "fyToken":"101000000010454",
                "productType":"CNC",
                "tradedQty":19,
                "tradePrice":14.1,
                "tradeValue":267.9,
                "tradeNumber":"3281523",
                "row":3281523,
                "symbol":"NSE:CENTRUM-EQ",
                "orderTag": "1:Ordertag"
              },
              {
                "clientId":"FXXXXX1",
                "orderDateTime":"07-Aug-2020 13:47:22",
                "orderNumber":"120080797993",
                "exchangeOrderNo": "1100000008047027",
                "exchange":10,
                "side":1,
                "segment":10,
                "orderType":2,
                "fyToken":"101000000018783",
                "productType":"CNC",
                "tradedQty":4,
                "tradePrice":115.5,
                "tradeValue":462.0,
                "tradeNumber":"27945307",
                "row":27945307,
                "symbol":"NSE:IDFNIFTYET-EQ",
                "orderTag": "1:Ordertag"
              }]
}

## [](https://myapi.fyers.in/docsv3#tag/Transaction-Info/paths/~1Transaction%20Info/options)Trades Filter By Order tag

You can query for a particular orderTag by passing the orderTag in the get parameters.

### Request samples

- cURL
- C#
- Java

Copy

Curl Request Method
curl -H "Authorization: app_id:access_token" https://api-t1.fyers.in/api/v3/tradebook?order_tag=1:Ordertag

-------------------------------------------------------------------
Sample Success Response
-------------------------------------------------------------------
{
  "s": "ok",
  "code": 200,
  "message": "",
  "tradeBook":
              [{
                "clientId":"FXXXXX",
                "orderDateTime":"07-Aug-2020 13:51:12",
                "orderNumber":"120080789075",
                "exchangeOrderNo": "1200000009204725",
                "exchange":10,
                "side":1,
                "segment":10,
                "orderType":2,
                "fyToken":"101000000010666",
                "productType":"CNC",
                "tradedQty":10,
                "tradePrice":32.7,
                "tradeValue":327.0,
                "tradeNumber":"52605023",
                "row":52605023,
                "symbol":"NSE:PNB-EQ",
                "orderTag": "1:Ordertag"
              },
              {
                "clientId":"FXXXXX",
                "orderDateTime":"07-Aug-2020 13:48:12",
                "orderNumber":"120080789139",
                "exchangeOrderNo": "1000000012031528",
                "exchange":10,
                "side":1,
                "segment":10,
                "orderType":2,
                "fyToken":"101000000010454",
                "productType":"CNC",
                "tradedQty":19,
                "tradePrice":14.1,
                "tradeValue":267.9,
                "tradeNumber":"3281523",
                "row":3281523,
                "symbol":"NSE:CENTRUM-EQ",
                "orderTag": "1:Ordertag"
              },
              {
                "clientId":"FXXXXX1",
                "orderDateTime":"07-Aug-2020 13:47:22",
                "orderNumber":"120080797993",
                "exchangeOrderNo": "1100000008047027",
                "exchange":10,
                "side":1,
                "segment":10,
                "orderType":2,
                "fyToken":"101000000018783",
                "productType":"CNC",
                "tradedQty":4,
                "tradePrice":115.5,
                "tradeValue":462.0,
                "tradeNumber":"27945307",
                "row":27945307,
                "symbol":"NSE:IDFNIFTYET-EQ",
                "orderTag": "1:Ordertag"
              }]
}

# [](https://myapi.fyers.in/docsv3#tag/Order-Placement-Guide)Order Placement Guide

## [](https://myapi.fyers.in/docsv3#tag/Order-Placement-Guide/Order-Placement-Guide)Order Placement Guide

The order placement process requires you to carefully input several parameters at the time of making the request. There are several validations which are required to be done before sending the request.

## [](https://myapi.fyers.in/docsv3#tag/Order-Placement-Guide/Order-Types)Order Types

- **Limit Order**
    
    - type: 1
    - A limit order allows you to buy or sell an asset at a specific price (limitPrice) or better. It will only be executed at the specified price or lower for a buy order, and at the specified price or higher for a sell order.
    
      
    
    Sample input:
    
    ```json
    { "symbol": "NSE:SBIN-EQ", "qty": 100, "type": 1, "side": 1, "productType": "INTRADAY", "limitPrice": 100, "stopPrice": 0, "validity": "DAY", "stopLoss": 0, "takeProfit": 0, "offlineOrder": false, "disclosedQty": 0 }
    ```
    
- **Market Order**
    
    - type: 2
    - A market order allows you to buy or sell an asset at the current market price. The limitPrice and stopPrice should be set to 0, as it is not used in this order type.
    
      
    
    Sample input:
    
    ```json
    { "symbol": "NSE:SBIN-EQ", "qty": 100, "type": 2, "side": 1, "productType": "INTRADAY", "limitPrice": 0, "stopPrice": 0, "validity": "DAY", "stopLoss": 0, "takeProfit": 0, "offlineOrder": false, "disclosedQty": 0 }
    ```
    
- **Stop Order / SL-M**
    
    - type: 3
    - A stop order is designed to limit losses on a position. It becomes a market order when the stopPrice is reached. The stopPrice is the trigger price at which the market order will be placed.
    - The stopPrice must not be higher than the Last Traded Price (ltp) for a sell order and not lower than the ltp for a buy order.
    
      
    
    Sample input:
    
    ```json
    { "symbol": "NSE:SBIN-EQ", "qty": 100, "type": 3, "side": 1, "productType": "INTRADAY", "limitPrice": 0, "stopPrice": 100, "validity": "DAY", "stopLoss": 0, "takeProfit": 0, "offlineOrder": false, "disclosedQty": 0 }
    ```
    
- **Stop Limit Order / SL-L**
    
    - type: 4
    - A stop-limit order combines features of a stop order and a limit order. It triggers a limit order once the stopPrice is reached.
    - The stopPrice must not be higher than the Last Traded Price (ltp) for a sell order and not lower than the ltp for a buy order.
    - The stopPrice must be lower than the limitPrice for a buy order and higher than the limitPrice for a sell order.
    
      
    
    Sample input:
    
    ```json
    { "symbol": "NSE:SBIN-EQ", "qty": 100, "type": 4, "side": 1, "productType": "INTRADAY", "limitPrice": 100, "stopPrice": 95, "validity": "DAY", "stopLoss": 0, "takeProfit": 0, "offlineOrder": false, "disclosedQty": 0 }
    ```
    

## [](https://myapi.fyers.in/docsv3#tag/Order-Placement-Guide/Product-Types)Product Types

- **Intraday**
    
    - Used to place orders which will be bought and sold the same day
    - Order type can be anything (Market, Limit, Stop, and Stop Limit)
- **CNC**
    
    - Used to place orders only in stocks which will be carried forward
    - Order type can be anything (Market, Limit, Stop, and Stop Limit)
- **Margin**
    
    - Used to place orders in derivative contracts which will be carried forward
    - Order type can be anything (Market, Limit, Stop, and Stop Limit)
- **Cover Order (CO)**
    
    - stopLoss is a mandatory input
    - stopLoss price is given in points denominated. (Eg: SBIN LTP = 300. For the above example, for buy CO, if you want to put stop loss as 298 then you have to pass "stopLoss" value as 2 (difference between ltp and your desired stop loss) )  
        Note:  
        1. "stopLoss" value can be float but should be multiple of 0.0500.  
        2. Now let's say if you don't provide stopLoss value as multiple of 0.0500 then you can find this error message {'code': -50, 'message': 'StopLoss not a multiple of tick size 0.0500', 's': 'error'}
    - The order type can be either market or limit (If the market order, then the stop loss price should not be higher than the ltp in buy and lower than the ltp for sell. If the limit order, then the stop loss price should not be higher than the limit price in buy and lower than the limit for sell)
    - Validity should be “DAY.”
    - Disclosed quantity should be 0.
- **Bracket Order (BO)**
    
    - stopLoss is a mandatory input
    - takeProfit is a mandatory input
    - The stopLoss and takeProfit are denominated in rupees above and below the trade price. (Eg: SBIN LTP = 300. So the user can give a target of Rs. 10 and stop loss or Rs. 5.)
    - Order type can be either market, limit, stop, or stop limit
    - Validity should be “DAY.”
    - Disclosed quantity should be 0
- **Margin Trading Facility (MTF)**
    
    - This order type is for placing trades with additional margin.
    - MTF orders require activation.
    - Only stocks from the approved MTF list are allowed.
    - Supported order types: Market, Limit, Stop, and Stop Limit.

## [](https://myapi.fyers.in/docsv3#tag/Order-Placement-Guide/Price-Validations)Price Validations

For all transaction requests (Order placement / modification), the price input should be in accordance with the exchange provided tick size for the particular symbol.

- Tick size is applicable for all price inputs (Limit / stop / stopLoss / target)
- Each symbol will have its own tick size
- All price inputs have to be in multiples of the tick size
- The tick size is available in the symbol master

## [](https://myapi.fyers.in/docsv3#tag/Order-Placement-Guide/Quantity-Validations)Quantity Validations

For all transaction requests (Order placement / modification), the quantity input should be in accordance with the exchange provided minimum lot size.

|Segment|Minimum Quantity Details|
|---|---|
|Equities|The quantity will be in multiples of 1|
|Equity Derivatives|The quantity will be in multiples of the lot size specified by the exchange|
|Currency Derivatives|The quantity will be in multiples of 1|
|Commodity Derivatives|The quantity will be in multiples of 1|

## [](https://myapi.fyers.in/docsv3#tag/Order-Placement-Guide/Order-Tag)Order Tag

For all Order placement requests where tags are passed they should meet following requirements.

- Ordertag string should be Alphanumeric i.e. no space or special characters will be allowed.
- Ordertag string should not exceed length of 30 characters and should have minimum length of 1 character.
- Ordertag string cannot be your **clientID** or string **Untagged**.
- Ordertagging is currently not supported for ProductType **BO** & **CO**. Orders with ordertag for CO/BO product Type will be rejeceted.

# [](https://myapi.fyers.in/docsv3#tag/Order-Placement)Order Placement

## [](https://myapi.fyers.in/docsv3#tag/Order-Placement/paths/~1OthePlacement/get)Single Order

This allows the user to place an order to any exchange via Fyers

## Request attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`symbol*`|string|Eg: NSE:SBIN-EQ|
|`qty*`|int|The quantity should be in multiples of lot size for derivatives.|
|`type*`|int|1. 1 => Limit Order<br>2. 2 => Market Order<br>3. 3 => Stop Order (SL-M)<br>4. 4 => Stoplimit Order (SL-L)<br>5. [View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Order-Types.)|
|`side*`|int|1. 1 => Buy<br>2. -1 => Sell<br>3. [View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Order-Sides)|
|`productType*`|string|1. CNC => For equity only<br>2. INTRADAY => Applicable for all segments.<br>3. MARGIN => Applicable only for derivatives<br>4. CO => Cover Order<br>5. BO => Bracket Order<br>6. MTF => Approved Symbols Only<br>7. [View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Product-Types.)|
|`limitPrice*`|float|Default => 0  <br>Provide valid price for Limit and Stoplimit orders|
|`stopPrice*`|float|Default => 0  <br>Provide valid price for Stop and Stoplimit orders|
|`disclosedQty*`|int|Default => 0  <br>Allowed only for Equity|
|`validity*`|string|IOC => Immediate or Cancel  <br>DAY => Valid till the end of the day|
|`offlineOrder*`|boolean|False => When market is open  <br>True => When placing AMO order|
|`stopLoss*`|float|Default => 0  <br>Provide valid price for CO and BO orders|
|`takeProfit*`|float|Default => 0  <br>Provide valid price for BO orders|
|`orderTag`|string|(Optional) Tag you want to assign to the specific order|

## Response attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`s`|string|ok / error|
|`code`|int|This is the code to identify specific responses  <br>If 201 comes in code it implies that order request has been made but no acknowledgement has been received in this case check orderbook before placing order|
|`message`|string|Message to clarify the request status.  <br>Eg: Order submitted successfully.  <br>Your Order Ref. No.119062829763|
|`id`|string|The order number of the placed order.  <br>Eg: 119031547242|

### Request samples

- cURL
- Python
- Node
- Web modular API
- C#
- Java

Copy

curl -H "Authorization:app_id:access_token" -H "Content-Type: application/json" -X POST -d '{
  "symbol":"MCX:SILVERMIC20NOVFUT",
  "qty":1,
  "type":2,
  "side":1,
  "productType":"INTRADAY",
  "limitPrice":0,
  "stopPrice":0,
  "validity":"DAY",
  "disclosedQty":0,
  "offlineOrder":false,
  "stopLoss":0,
  "takeProfit":0,
  "orderTag":"tag1"
}' https://api-t1.fyers.in/api/v3/orders/sync

------------------------------------------------------------------------------------------------------------------------------------------
Sample Success Response 
------------------------------------------------------------------------------------------------------------------------------------------
 {
  "s": "ok",
  "code": 1101,
  "message": "Order submitted successfully. Your Order Ref. No.808058117761",
  "id":"808058117761"
  }

## [](https://myapi.fyers.in/docsv3#tag/Order-Placement/paths/~1OthePlacement/patch)Multi Order

You can place upto 10 orders simultaneously via the API.  
While Placing Multi orders you need to pass an ARRAY containing the orders request attributes

Sample Request :

```
[{ "symbol":"MCX:SILVERM20NOVFUT", "qty":1, "type":1, "side":1, "productType":"INTRADAY", "limitPrice":61050, "stopPrice":0 , "disclosedQty":0, "validity":"DAY", "offlineOrder":"False", "stopLoss":0, "takeProfit":0, "orderTag":"tag1" }, { "symbol":"MCX:SILVERM20NOVFUT", "qty":1, "type":2, "side":1, "productType":"INTRADAY", "limitPrice":61050, "stopPrice":0 , "disclosedQty":0, "validity":"DAY", "offlineOrder":"False", "stopLoss":0, "takeProfit":0, "orderTag":"tag1" }]
```

### Request samples

- cURL
- Python
- Node
- Web modular API
- C#
- Java

Copy

curl -H "Authorization:appId:access_token" -H "Content-Type: application/json" -X POST -d '[
  {
    "symbol":"NSE:ITC-EQ",
    "qty":1,
    "type":1,
    "side":1,
    "productType":"INTRADAY",
    "limitPrice":165,
    "stopPrice":0,
    "disclosedQty":0,
    "validity":"DAY",
    "offlineOrder":true,
    "stopLoss":0,
    "takeProfit":0,
    "orderTag":"tag1"
  },
  {
    "symbol":"NSE:ITC-EQ",
    "qty":1,
    "type":1,
    "side":1,
    "productType":"INTRADAY",
    "limitPrice":165.10,
    "stopPrice":0,
    "disclosedQty":0,
    "validity":"DAY",
    "offlineOrder":true,
    "stopLoss":0,
    "takeProfit":0,
    "orderTag":"tag1"
  },
  {
    "symbol":"NSE:ITC-EQ",
    "qty":1,
    "type":1,
    "side":1,
    "productType":"INTRADAY",
    "limitPrice":165.10,
    "stopPrice":0,
    "disclosedQty":0,
    "validity":"DAY",
    "offlineOrder":true,
    "stopLoss":0,
    "takeProfit":0,
    "orderTag":"tag1"
  }
]' https://api-t1.fyers.in/api/v3/multi-order/sync

------------------------------------------------------------------------------------------------------------------------------------------
Sample Success Response 
------------------------------------------------------------------------------------------------------------------------------------------
 {
    "s": "ok",
    "code": 200,
    "message": "",
    "data": [{"statusCode": 200,
              "body": {
                        "s": "ok",
                        "code": 200,
                        "message": "Order submitted successfully. 
                                    Your Order Ref. No. 120080778988",
                        "id": "120080778988"
                      },
              "statusDescription": "HTTP OK"
            },
            {
              "statusCode": 200,
              "body": 
                      {
                        "s": "ok",
                        "code": 200,
                        "message": "Order submitted successfully. 
                                    Your Order Ref. No.120080777359",
                        "id": "120080777359"
                      },
              "statusDescription": "HTTP OK"
            },
            {
              "statusCode": 200,
              "body": 
                      {
                        "s": "ok",
                        "code": 200,
                        "message": "Order submitted successfully. 
                                    Your Order Ref. No.120080777379",
                        "id": "120080777379"
                      }, "statusDescription": "HTTP OK"
              }]
  }

## [](https://myapi.fyers.in/docsv3#tag/Order-Placement/paths/~1OthePlacement/put)MultiLeg Order

This allows the user to place an MultiLeg order to NSE via Fyers.  
**Note:** As per exchange mandate, while selecting symbols please check the "stream" key in the [symbol master JSON file](https://myapi.fyers.in/docsv3#tag/Broker-Config/paths/~1Broker%20Config/put) to ensure both legs belong to the same stream.  

## Request attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`orderTag`|string|(Optional) Tag you want to assign to the specific order|
|`productType*`|string|1. INTRADAY => Applicable for NFO segments.<br>2. MARGIN => Applicable for NFO segments.|
|`offlineOrder*`|boolean|False => When market is open  <br>True => When placing AMO order.|
|`orderType*`|string|1. 3L => Applicable for 3 leg order.<br>2. 2L => Applicable for 2 leg order.|
|`validity*`|string|IOC => Immediate or Cancel|
|`legs*`|json|It represents multiple trading legs in a multi-leg order. Each leg within the legs object corresponds to a specific trading instrument and order details. Each leg is identified by a unique key (leg1, leg2, leg3 )|

## Leg attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`symbol*`|string|Eg: NSE:SBIN24JUNFUT|
|`qty*`|int|The quantity should be in multiples of lot size for derivatives.|
|`side*`|int|1. 1 => Buy<br>2. -1 => Sell|
|`type*`|int|1. 1 => Limit Order|
|`limitPrice*`|float|Provide valid price for Limit orders|

## Response attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`s`|string|ok / error|
|`code`|int|This is the code to identify specific responses  <br>If 201 comes in code it implies that order request has been made but no acknowledgement has been received in this case check orderbook before placing order|
|`message`|string|Message to clarify the request status.  <br>Eg: Order submitted successfully.  <br>Your Order Ref. No.119062829763|
|`id`|string|The order number of the placed order.  <br>Eg: 119031547242|

## Input Validations

|**Error Message**|**Description**|
|---|---|
|`The input symbol is invalid.`|Input symbol ticker is not found in the exchange data|
|`Only NFO symbols are allowed`|Options and Future symbols listed in NSE are allowed.|
|`The input symbol is banned for FNO trading.`|The input symbol is banned for trading by the exchange.|
|`All symbols must be related to the same underlying symbol.`|All symbols must be related to same symbol|
|`Quantity should be multiples of the lot size.`|Input qty(Quantity) should be multiples of minimum lot size of that symbol|
|`You cannot add same symbol for two legs.`|Input data should not have same symbol in more than one leg.|
|`Group combination not found`|Input Symbols do not belong to same [stream group.](https://myapi.fyers.in/docsv3#tag/Broker-Config/paths/~1Broker%20Config/put)|

### Request samples

- cURL
- Python
- Node
- C#
- Java

Copy

curl -H "Authorization:app_id:access_token" -H "Content-Type: application/json" -X POST -d '{
  "orderTag": "tag1",
  "productType": "MARGIN",
  "offlineOrder": false,
  "orderType": "3L",
  "validity": "IOC",
  "legs": {
      "leg1": {
        "symbol": "NSE:SBIN24JUNFUT",
        "qty": 750,
        "side": 1,
        "type": 1,
        "limitPrice": 800
      },
      "leg2": {
          "symbol": "NSE:SBIN24JULFUT",
          "qty": 750,
          "side": 1,
          "type": 1,
          "limitPrice": 800
      },
      "leg3": {
          "symbol": "NSE:SBIN24JUN900CE",
          "qty": 750,
          "side": 1,
          "type": 1,
          "limitPrice": 3
      }
  }
}' https://api-t1.fyers.in/api/v3/multileg/orders/sync

------------------------------------------------------------------------------------------------------------------------------------------
Sample Success Response 
------------------------------------------------------------------------------------------------------------------------------------------
 {
  "s": "ok",
  "code": 1101,
  "message": "Successfully placed order",
  "id":"808058117761"
  }

# [](https://myapi.fyers.in/docsv3#tag/GTT-Orders)GTT Orders

GTT (Good Till Trigger) is used to create orders with longer validity. It helps you set a Target or Stop-Loss for your open positions or holdings, and you can also use it to take new positions. The order remains active for up to one year.

## [](https://myapi.fyers.in/docsv3#tag/GTT-Orders/paths/~1GTT%20Orders/post)GTT Single

This type is used to create a single GTT order.

- It supports placing orders for CNC, Margin, and MTF.
- It can be applied either as a Target or Stop Loss for your existing holdings/positions.
- Alternatively, it can be used to create a GTT order for a new position/holding.

  

## Request attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`id*`|string|Unique identifier for the order to be modified, e.g., "25010700000001".|
|`Side`|integer|Indicates the side of the order: `1` for buy, `-1` for sell.|
|`symbol*`|string|The instrument's unique identifier, e.g., "NSE:CHOLAFIN-EQ"|
|`productType*`|string|The product type for the order. Valid values: "CNC", "MARGIN", "MTF".|
|`orderInfo*`|object|Contains information about the GTT/OCO order legs.|
|`orderInfo.leg1*`|object|Details for GTT order leg. Mandatory for all orders.|
|`orderInfo.leg1.price*`|number|Price at which the order|
|`orderInfo.leg1.triggerPrice`|number|Trigger price for the GTT order.  <br>NOTE: for OCO order this leg trigger price should be always above LTP|
|`orderInfo.leg1.qty*`|integer|Quantity for the GTT order leg.|
|`orderInfo.leg2*`|object|Details for OCO order leg. Optional and included only for OCO orders.|
|`orderInfo.leg2.price*`|number|Price at which the second leg of the OCO order should be placed.|
|`orderInfo.leg2.triggerPrice*`|number|Trigger price for the second leg of the OCO order.  <br>NOTE: for OCO order this leg trigger price should be always below LTP|
|`orderInfo.leg2.qty*`|integer|Quantity for the second leg of the OCO order..|

## Response attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`code`|integer|Status code indicating the outcome of the request:  <br>- `1101`: Order placed successfully.  <br>- `201`: Order is in transit. Confirm details using the Orderbook API.  <br>- Other codes represent specific error conditions.|
|`message*`|string|Descriptive message about the request status, e.g., "Successfully placed order".|
|`s*`|string|Request status indicator: "ok" for success, "error" for failure.|
|`id*`|string|Unique identifier for the placed order, returned when the order is successfully processed.|

### Request samples

- cURL
- Python
- Node
- Web Modular API
- C#
- Java

Copy

curl --location 'https://api-t1.fyers.in/api/v3/gtt/orders/sync' \
--header 'Authorization: accessToken' \
--header 'Content-Type: application/json' \
--data '{
    "side": 1,
    "symbol": "NSE:SBIN-EQ",
    "productType":"CNC",
    "orderInfo": {
        "leg1": {
        "price": 1000,
        "triggerPrice": 1000,
        "qty": 1
        }
    }
}'
------------------------------------------------------------------------------------------------------------------------------------------
Sample Success Response 
------------------------------------------------------------------------------------------------------------------------------------------
{
  "code": 1101,
  "message": "Successfully placed order",
  "s": "ok",
  "id":"25012400002074"
  }

## [](https://myapi.fyers.in/docsv3#tag/GTT-Orders/paths/~1GTT%20Orders/put)GTT OCO

This type allows you to place both a Stop Loss and a Target order simultaneously. If one order is triggered, the other gets automatically canceled.  

To avoid rejections:

- For Leg1: The trigger price must always be greater than the LTP
- For Leg 2: The trigger price must always be less than the LTP

## Request attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`id*`|string|Unique identifier for the order to be modified, e.g., "25010700000001".|
|`Side`|integer|Indicates the side of the order: `1` for buy, `-1` for sell.|
|`symbol*`|string|The instrument's unique identifier, e.g., "NSE:CHOLAFIN-EQ"|
|`productType*`|string|The product type for the order. Valid values: "CNC", "MARGIN", "MTF".|
|`orderInfo*`|object|Contains information about the GTT/OCO order legs.|
|`orderInfo.leg1*`|object|Details for GTT order leg. Mandatory for all orders.|
|`orderInfo.leg1.price*`|number|Price at which the order|
|`orderInfo.leg1.triggerPrice`|number|Trigger price for the GTT order.  <br>NOTE: for OCO order this leg trigger price should be always above LTP|
|`orderInfo.leg1.qty*`|integer|Quantity for the GTT order leg.|
|`orderInfo.leg2*`|object|Details for OCO order leg. Optional and included only for OCO orders.|
|`orderInfo.leg2.price*`|number|Price at which the second leg of the OCO order should be placed.|
|`orderInfo.leg2.triggerPrice*`|number|Trigger price for the second leg of the OCO order.  <br>NOTE: for OCO order this leg trigger price should be always below LTP|
|`orderInfo.leg2.qty*`|integer|Quantity for the second leg of the OCO order..|

## Response attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`code`|integer|Status code indicating the outcome of the request:  <br>- `1101`: Order placed successfully.  <br>- `201`: Order is in transit. Confirm details using the Orderbook API.  <br>- Other codes represent specific error conditions.|
|`message*`|string|Descriptive message about the request status, e.g., "Successfully placed order".|
|`s*`|string|Request status indicator: "ok" for success, "error" for failure.|
|`id*`|string|Unique identifier for the placed order, returned when the order is successfully processed.|

### Request samples

- cURL
- Python
- Node
- Web Modular API
- C#
- Java

Copy

curl --location 'https://api-t1.fyers.in/api/v3/gtt/orders/sync' \
--header 'Authorization: accessToken' \
--header 'Content-Type: application/json' \
--data '{
    "side": 1,
    "symbol": "NSE:CHOLAFIN-EQ",
    "productType":"CNC",
    "orderInfo": {
        "leg1": {
            "price": 10000,
            "triggerPrice": 10000,
            "qty": 1
        },
        "leg2": {
            "price": 990,
            "triggerPrice": 990,
            "qty": 3
        }
    }
}'
------------------------------------------------------------------------------------------------------------------------------------------
Sample Success Response 
------------------------------------------------------------------------------------------------------------------------------------------
{
  "code": 1101,
  "message": "Successfully placed order",
  "s": "ok",
  "id":"25012400002074"
  }

## [](https://myapi.fyers.in/docsv3#tag/GTT-Orders/paths/~1GTT%20Orders/patch)GTT Modify Order

This allows the user to modify pending GTT orders. Users can provide parameters which need to be modified. In case a particular parameter has not been provided, the original value will be considered.  

## Request attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`id*`|string|Unique identifier for the order to be modified, e.g., "25010700000001".|
|`orderInfo*`|object|Contains updated information about the GTT/OCO order legs.|
|`orderInfo.leg1*`|object|Details for GTT order leg. Mandatory for all modifications.|
|`orderInfo.leg1.price*`|number|Updated price at which the order should be placed.|
|`orderInfo.leg1.triggerPrice*`|number|Updated trigger price for the GTT order. NOTE: for OCO order this leg trigger price should be always above LTP.|
|`orderInfo.leg1.qty*`|integer|Updated quantity for the GTT order leg.|
|`orderInfo.leg2*`|object|Details for OCO order leg. Required if the order is an OCO type.|
|`orderInfo.leg2.price*`|number|Updated price for the second leg of the OCO order.|
|`orderInfo.leg2.triggerPrice*`|number|Updated trigger price for the second leg of the OCO order.  <br>NOTE: for OCO order this leg trigger price should be always below LTP.|
|`orderInfo.leg2.qty*`|integer|Updated quantity for the second leg of the OCO order.|

## Response attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`s`|string|ok / error|
|`code`|int|Status code indicating the outcome of the modification request:  <br>- 1102: Order modification successful.  <br>- 201: Order modification is in transit. Confirm details using the Orderbook API.  <br>- Other codes represent specific error conditions.|
|`message`|string|Descriptive message about the modification request.  <br>e.g., "Successfully modified order".|
|`id`|string|Unique identifier for the modified order, returned if the modification is successful.|

### Request samples

- cURL
- Python
- Node
- Web Modular API
- C#
- Java

Copy

curl --location --request PATCH 'https://api-t1.fyers.in/api/v3/gtt/orders/sync' \
--header 'Authorization: accesstoken' \
--header 'Content-Type: application/json' \
--data '{
        "id": "25012400002074",
        "orderInfo": {
            "leg1": {
                "price": 1010,
                "triggerPrice": 1010,
                "qty": 5
            },
            "leg2": {
                "price": 1010,
                "triggerPrice": 1010,
                "qty": 5
            }
        }
}'
------------------------------------------------------------------------------------------------------------------------------------------
Sample Success Response 
------------------------------------------------------------------------------------------------------------------------------------------
  {  
  "code": 1102,
  "message": "Successfully modified order',
  "s": "ok", 
  "id": '25012400002074"
  }

## [](https://myapi.fyers.in/docsv3#tag/GTT-Orders/paths/~1GTT%20Orders/get)GTT Cancel Order

You can cancel pending orders before they trigger.

## Request attributes - For each order

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`id*`|string|Unique identifier for the order to be cancelled,  <br>e.g., "25010700000001".|

## Response attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`s`|string|ok / error|
|`code`|int|Status code indicating the outcome of the cancellation request:  <br>- 1103: Order cancellation successful.  <br>- Other codes represent specific error conditions.|
|`message`|string|Descriptive message about the cancellation request,  <br>e.g., "Successfully|
|`id`|string|Unique identifier for the cancelled order, returned if the cancellation is successful.|

### Request samples

- cURL
- Python
- Node
- Web Modular API
- C#
- Java

Copy

curl --location --request DELETE 'https://api-t1.fyers.in/api/v3/gtt/orders/sync' \
--header 'Authorization: accesstoken' \
--header 'Content-Type: application/json' \
--data '{"id":"25012400002099"}'

---------------------------------------------------------------------------------------------------------------------------------------------
Sample Success Response 
------------------------------------------------------------------------------------------------------------------------------------------
{
  "code": 1103,
  "message": "Successfully cancelled order",
  "s": "ok",
  "id": "25012400002099"
}

## [](https://myapi.fyers.in/docsv3#tag/GTT-Orders/paths/~1GTT%20Orders/options)GTT Order Book

You can fetch all pending GTT Orders.

## Response attributes - For each order

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`code`|integer|Status code of the API response:  <br>- 200: Request successful.  <br>- Other codes represent specific error conditions.|
|`message`|string|Optional message about the API request (can be empty for successful requests).|
|`s`|string|Status of the request: "ok" for success, "error" for failure.|
|`orderBook`|array|List of order details.|
|`orderBook[].client_id`|string|Client identifier associated with the order.|
|`orderBook[].exchange`|integer|Exchange code where the order is placed, e.g., 10 for NSE.|
|`orderBook[].fy_token`|string|Unique token for the instrument in the order.|
|`orderBook[].id_fyers`|string|Fyers system-generated unique identifier for the order.|
|`orderBook[].id`|string|Order ID provided by the system.|
|`orderBook[].instrument`|integer|Instrument type, e.g., 0 for equity.|
|`orderBook[].lot_size`|integer|Lot size of the instrument in the order.|
|`orderBook[].multiplier`|integer|Multiplier for the instrument (e.g., for derivatives).|
|`orderBook[].ord_status`|integer|Order status code: -- 1: Cancelled -<br>- 2: Traded / Filled -<br>- 3: For future use -<br>- 4: Transit -<br>- 5: Rejected -<br>- 6: Pending|
|`orderBook[].precision`|integer|Decimal precision for the instrument's price.|
|`orderBook[].price_limit`|number|Limit price for the first leg of the order.|
|`orderBook[].price2_limit`|number|Limit price for the second leg (if OCO).|
|`orderBook[].price_trigger`|number|Trigger price for the first leg of the order.|
|`orderBook[].price2_trigger`|number|Trigger price for the second leg (if OCO).|
|`orderBook[].product_type`|string|Product type, e.g., "CNC", "MARGIN", "MTF".|
|`orderBook[].qty`|integer|Quantity for the first leg of the order.|
|`orderBook[].qty2`|integer|Quantity for the second leg (if OCO).|
|`orderBook[].report_type`|string|Status of the order, e.g., "CANCELLED", "PLACED".|
|`orderBook[].segment`|integer|Segment code, e.g., 10 for equity.|
|`orderBook[].symbol`|string|Symbol of the instrument, e.g., "NSE:CHOLAFIN-EQ".|
|`orderBook[].symbol_desc`|string|Full description of the symbol,  <br>e.g., "CHOLAMANDALAM IN & FIN CO".|
|`orderBook[].symbol_exch`|string|Symbol short code on the exchange, e.g., "CHOLAFIN".|
|`orderBook[].tick_size`|number|Minimum price increment for the instrument.|
|`orderBook[].tran_side`|integer|Transaction side: 1 for buy, -1 for sell.|
|`orderBook[].gtt_oco_ind`|integer|Indicator for the order type: -  <br>1: GTT order.  <br>2: OCO order.|
|`orderBook[].create_time`|string|Creation timestamp of the order in human-readable format.|
|`orderBook[].create_time_epoch`|integer|Creation timestamp of the order in epoch seconds.|
|`orderBook[].oms_msg`|string|Message from the Order Management System (OMS) about the order's status.|
|`orderBook[].ltp_ch`|number|Last traded price change.|
|`orderBook[].ltp_chp`|number|Last traded price change percentage.|
|`orderBook[].ltp`|number|Last traded price of the instrument.|

### Request samples

- cURL
- Python
- Node
- Web Modular API
- C#
- Java

Copy

curl --location 'https://api-t1.fyers.in/api/v3/gtt/orders' \
--header 'Authorization: accesstoken' \

---------------------------------------------------------------------------------------------------------------------------------------------
Sample Success Response 
---------------------------------------------------------------------------------------------------------------------------------------------
Response structure:
{
  "s": "ok",
  "code": 200,
  "message": "",
  "orderBook": [
    {
      "clientId": "X******",
      "exchange": 10,
      "fy_token": "10100000003045",
      "id_fyers": "c6697c04-d9ab-4a7c-a6f4-b0cc4ca698f6",
      "id": "25012400002074",
      "instrument": 0,
      "lot_size": 1,
      "multiplier": 0,
      "ord_status": 1,
      "precision": 2,
      "price_limit": 1020,
      "price2_limit": 620,
      "price_trigger": 1020,
      "price2_trigger": 620,
      "product_type": "CNC",
      "qty": 5,
      "qty2": 5,
      "report_type": "CANCELLED",
      "segment": 10,
      "symbol": "NSE:SBIN-EQ",
      "symbol_desc": "STATE BANK OF INDIA",
      "symbol_exch": "SBIN",
      "tick_size": 0.05,
      "tran_side": 1,
      "gtt_oco_ind": 2,
      "create_time": "24-Jan-2025 16:13:31",
      "create_time_epoch": 1737715411,
      "oms_msg": "GTT/OCO order cancelled successfully.",
      "ltp_ch": 0,
      "ltp_chp": 0,
      "ltp": 0
    },
    {
      "clientId": "X******",
      "exchange": 10,
      "fy_token": "10100000003045",
      "id_fyers": "142849a0-d32b-44b5-9108-b7db5ee5e59b",
      "id": "25012400002099",
      "instrument": 0,
      "lot_size": 1,
      "multiplier": 0,
      "ord_status": 1,
      "precision": 2,
      "price_limit": 1000,
      "price2_limit": 600,
      "price_trigger": 1000,
      "price2_trigger": 600,
      "product_type": "MTF",
      "qty": 3,
      "qty2": 3,
      "report_type": "CANCELLED",
      "segment": 10,
      "symbol": "NSE:SBIN-EQ",
      "symbol_desc": "STATE BANK OF INDIA",
      "symbol_exch": "SBIN",
      "tick_size": 0.05,
      "tran_side": -1,
      "gtt_oco_ind": 2,
      "create_time": "24-Jan-2025 16:10:27",
      "create_time_epoch": 1737715227,
      "oms_msg": "GTT/OCO order cancelled successfully.",
      "ltp_ch": 0,
      "ltp_chp": 0,
      "ltp": 0
    }
  ]
}

# [](https://myapi.fyers.in/docsv3#tag/Other-Transactions)Other Transactions

## [](https://myapi.fyers.in/docsv3#tag/Other-Transactions/paths/~1OtherTransactions/post)Modify Orders

This allows the user to modify a pending order. User can provide parameters which needs to be modified. In case a particular parameter has not been provided, the original value will be considered.

## Request attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`id*`|string|Mandatory.  <br>Eg: 119031547242|
|`type*`|int|Mandatory.|
|`limitPrice`|float|Mandatory. Only incase of Limit/ Stoplimit orders|
|`stopPrice`|float|Mandatory. Only incase of Stop/ Stoplimit orders|
|`qty`|int|Mandatory. Incase you want to modify the quantity|
|`disclosedQty`|int|Disclosed quantity (Optional)|

## Response attributes

|**Attribute**|**Data Type**|*_Description_|
|---|---|---|
|`s`|string|ok / error|
|`code`|int|This is the code to identify specific responses  <br>If 201 comes in code it implies that order request has been made but no acknowledgement has been received in this case check orderbook before placing order|
|`message`|string|Message to clarify the request status.  <br>Eg: Successfully modified order|
|`id`|string|The order number of the modified order  <br>Eg: 119031547242|

### Request samples

- cURL
- Python
- Node
- Web modular API
- C#
- Java

Copy

curl -H "Authorization:app_id:access_token" -H "Content-Type: application/json" -X PATCH -d '{
  "id": "809229222111",
  "qty": 1,
  "type": 2,
  "side": 1,
  "limitPrice": 61200
}' https://api-t1.fyers.in/api/v3/orders/sync

------------------------------------------------------------------------------------------------------------------------------------------
Sample Success Response 
------------------------------------------------------------------------------------------------------------------------------------------
 {
  "s": "ok",
  "code": 1101,
  "message": "Successfully modified order', 'id': '808058117761"
}

## [](https://myapi.fyers.in/docsv3#tag/Other-Transactions/paths/~1OtherTransactions/get)Modify Multi Orders

You can modify upto 10 orders simultaneously via the API.  
While Modifying Multi orders you need to pass an ARRAY containing the orders request attributes

Sample Request :

[{
    "id":orderId,
    "type":1,
    "limitPrice": 61049,
    "qty":1
  },
  {
    "id":orderId,
    "type":1,
    "limitPrice": 61049,
    "qty":1 
  }]

### Request samples

- Python
- Node
- Web modular API
- C#
- Java

Copy

from fyers_apiv3 import fyersModel

client_id = "XC4XXXXM-100"
access_token = "eyJ0eXXXXXXXX2c5-Y3RgS8wR14g"
# Initialize the FyersModel instance with your client_id, access_token, and enable async mode
fyers = fyersModel.FyersModel(client_id=client_id, token=access_token,is_async=False, log_path="")

data = [{
  "id": 8102710298291,
  "type": 1,
  "limitPrice": 61049,
  "qty": 1
},
{
  "id": 8102710298292,
  "type": 1,
  "limitPrice": 61049,
  "qty": 1
}]

response = fyers.modify_basket_orders(data=data)
print(response)
------------------------------------------------------------------------------------------------------------------------------------------
Sample Success Response 
------------------------------------------------------------------------------------------------------------------------------------------
 {
  "s": "ok",
  "code": 200,
  "message": "",
  "data": [{"statusCode": 200,
            "body": {
                        "s": "ok",
                        "code": 200,
                        "message": "Successfully modified order",
                        "id": 8102710298291
                      },
                      "statusDescription": "HTTP OK"
              },
              {
                "statusCode": 200,
                "body": {
                          "s": "ok",
                          "code": 200,
                          "message": "Successfully modified order",
                          "id": 8102710298292
                        },
                        "statusDescription": "HTTP OK"
              }
            ]}

  }

## [](https://myapi.fyers.in/docsv3#tag/Other-Transactions/paths/~1OtherTrans/put)Cancel Order

Cancel pending orders

## Request attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`id*`|string|Mandatory.  <br>Eg: 119031547242|

## Response attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`s`|string|ok / error|
|`code`|int|This is the code to identify specific responses  <br>If 201 comes in code it implies that order request has been made but no acknowledgement has been received in this case check orderbook before placing order|
|`message`|string|Message to clarify the request status.  <br>Eg: Successfully canceled order|
|`id`|string|The order number of the canceled order.  <br>Eg: 119031547242|

### Request samples

- cURL
- Python
- Node
- Web modular API
- C#
- Java

Copy

curl -H "Authorization:app_id:access_token" -H "Content-Type: application/json" -X DELETE -d '{
  "id": "52009227353"
}' https://api-t1.fyers.in/api/v3/orders/sync

---------------------------------------------------------------------------------------------------------------------------------------------
Sample Success Response 
------------------------------------------------------------------------------------------------------------------------------------------
{
  "s": "ok",
  "code": 1103,
  "message": "Successfully cancelled order",
  "id": "808058117761"
}

## [](https://myapi.fyers.in/docsv3#tag/Other-Transactions/paths/~1OtherTrans/delete)Cancel Multi Order

You can cancel upto 10 orders simultaneously via the API.  
While cancelling Multi orders you need to pass an ARRAY containing the orders request attributes

Sample Request :

[{ 
  "id":orderId
  },
  {
  "id":orderId
}]
 

### Request samples

- Python
- Node
- Web modular API
- C#
- Java

Copy

from fyers_apiv3 import fyersModel

client_id = "XC4XXXXM-100"
access_token = "eyJ0eXXXXXXXX2c5-Y3RgS8wR14g"

# Initialize the FyersModel instance with your client_id, access_token, and enable async mode
fyers = fyersModel.FyersModel(client_id=client_id, token=access_token,is_async=True, log_path="")

data =  [{
    "id": '808058117761'
},
{
    "id": '808058117762'
}]

response = fyers.cancel_basket_orders(data=data)
print(response)

 ---------------------------------------------------------------------------------------------------------------------------------------------
 Sample Success Response 
 ------------------------------------------------------------------------------------------------------------------------------------------
{
   "s":ok,
   "code": 200,
   "message": "",
   "data": [{"statusCode": 200,
               "body": 
                     {
                     "s":ok,
                     "code": 1103,
                     "message": "Successfully cancelled order",
                     "id": "808058117761"
                     },"statusDescription": "HTTP OK"
             },
             {
               "statusCode": 200,
               "body": 
                     {
                       "s":ok,
                       "code": 1103,
                       "message": "Successfully cancelled order",
                       "id": "808058117762"
                     }, "statusDescription": "HTTP OK"
             }
           ]
 }

## [](https://myapi.fyers.in/docsv3#tag/Other-Transactions/paths/~1OtherTrans/patch)Exit Position

This allows the user to either exit all open positions or any specific open position.

## Request attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`Id`|string|In case id is not passed, then all the open positions will be closed|

## Response attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`s`|string|ok / error|
|`code`|int|This is the code to identify specific responses .  <br>If 201 comes in code it implies that counter order has been placed but not filled due to low liquidity or any other reason|
|`message`|string|Message to clarify the request status.  <br>Eg:All positions are closed|

Sample Request :

  {
    "id": [positionId1,positionId2]
  }

### Request samples

- cURL
- Python
- Node
- Web modular API
- C#
- Java

Copy

curl -H "Authorization:app_id:access_token" -H "Content-Type: application/json" -X DELETE -d '{"exit_all":1}' https://api-t1.fyers.in/api/v3/positions 
------------------------------------------------------------------------------------------------------------------------------------------
  Sample Success Response 
------------------------------------------------------------------------------------------------------------------------------------------
{
 "s": "ok",
 "code": 200,
 "message": "The position is closed."
}

## [](https://myapi.fyers.in/docsv3#tag/Other-Transactions/paths/~1OtherTrans/options)Exit Position - By Id

## Request attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`id`|string or [string]|Optional  <br>Eg: NSE:SBIN-EQ-BO  <br>This will only exit the open positions for a particular position id or list of position id provided like ["NSE:SBIN-EQ-INTRADAY","NSE:SBIN-EQ-CNC"]|

### Request samples

- cURL
- Python
- Node
- Web modular API
- C#
- Java

Copy

curl -H "Authorization:app_id:access_token" -H "Content-Type: application/json" -X DELETE -d '{"id":"NSE:SBIN-EQ-BO"}' https://api-t1.fyers.in/api/v3/positions

## [](https://myapi.fyers.in/docsv3#tag/Other-Transactions/paths/~1OtherTrans/head)Exit Position - By Segment Side & productType

## Request attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`segment*`|[ int ]|**Mandatory**  <br>In the API , to close your position for a specific segment, you need to use the "segment" parameter with one of the following possible values: 10(Capital Market),11(Equity Derivatives),12(Currency Derivatives),20(Commodity Derivatives). Eg: [10,12]|
|`side*`|[ int]|**Mandatory**  <br>In the API , to close your position for a specific side, you need to use the "side" parameter with one of the following possible values: 1(Buy side),-1(Sell side). Eg: [1,-1]|
|`productType*`|[ string ]|**Mandatory**  <br>In the API , to close your position for a specific orderType, you need to use the "productType" parameter with one of the following possible values: "INTRADAY","CNC","CO","BO","MARGIN","ALL". Eg: ["INTRADAY","CNC"]|

### Request samples

- cURL
- Python
- Node
- Web modular API
- C#
- Java

Copy

curl -H "Authorization:app_id:access_token" -H "Content-Type: application/json" -X DELETE -d '{"segment":[10],"side":[1,-1],"productType":["INTRADAY","CNC"]}' https://api-t1.fyers.in/api/v3/positions

## [](https://myapi.fyers.in/docsv3#tag/Other-Transactions/paths/~1OtherTrans/get)Pending Order Cancel

This is an added functionality for exit position API. If a user has open positions in particular stocks and also working opposite order of the particular stock, the user can close the working orders and then exit the open positions.  
  
**Endpoint:** [https://api-t1.fyers.in/api/v3/positions](https://api-t1.fyers.in/api/v3/positions)  
  
The following should be passed in the body of the DELETE method of positions to cancel the pending orders:  
  

{"pending_orders_cancel": 1} 

If only a single symbol's order and position needs to be cancelled, the position ID should also be sent in the body:  
  

{"id": "NSE:SBIN-EQ-INTRADAY","pending_orders_cancel": 1}

### Request samples

- cURL

Copy

curl -H "Authorization:app_id:access_token" -H "Content-Type: application/json" -X DELETE -d '{"pending_orders_cancel": 1}' https://api-t1.fyers.in/api/v3/positions

---------------------------------------------------------------------------------------------------------------------------------------------
  Sample Success Response 
---------------------------------------------------------------------------------------------------------------------------------------------
{
 "s": "ok",
 "code": 200,
 "message": "The position is closed."
}

## [](https://myapi.fyers.in/docsv3#tag/Other-Transactions/paths/~1OthePlacement/post)Convert Position

This allows the user to convert an open position from one product type to another.

## Request attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`symbol*`|string|Mandatory. pass the position id here  <br>Eg: NSE:SBIN-EQ-INTRADAY|
|`overnight*`|int|Mandatory. if the position to be converted is a carry forward position, then send overnight flag as 1. If the position is taken today, irrespective of its product type, then send overnight flag as 0|
|`positionSide*`|int|Mandatory. 1 => Open long positions  <br>-1 => Open short positions  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Position-Sides)|
|`convertQty*`|int|Mandatory. Quantity to be converted. Has to be in multiples of lot size for derivatives|
|`convertFrom*`|string|Mandatory. Existing productType  <br>(CNC positions cannot be converted)  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Product-Types.)|
|`convertTo*`|string|Mandatory. The new product type  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Product-Types.)|

**Notes**

1. CNC, CO, BO, and MTF positions cannot be converted.
2. You cannot convert positions to CO, BO,MTF.

## Response attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`s`|string|ok / error|
|`code`|int|This is the code to identify specific responses|
|`message`|string|Message to clarify the request status.  <br>Eg: You cannot convert CNC position to INTRADAY / MARGIN.|

### Request samples

- cURL
- Python
- Node
- Web modular API
- C#
- Java

Copy

curl -H "Authorization:app_id:access_token" -H "Content-Type: application/json" -X POST -d '{
  "symbol": "MCX:SILVERMIC20NOVFUT-INTRADAY",
  "positionSide": 1,
  "convertQty": 1,
  "convertFrom": "INTRADAY",
  "convertTo": "CNC",
  "overnight": 1
}' https://api-t1.fyers.in/api/v3/positions

------------------------------------------------------------------------------------------------------------------------------------------
Sample Success Response 
------------------------------------------------------------------------------------------------------------------------------------------
 {
  "s": "ok",
  "code": 200,
  "message": "Position Converted Successfully!!",
  "positionDetails": 1101
}

# [](https://myapi.fyers.in/docsv3#tag/Margin-Calculator)Margin Calculator

## [](https://myapi.fyers.in/docsv3#tag/Margin-Calculator/paths/~1MarginCalculator/post)Span Margin Calculator

Span margin API will calculate the span margin and exposure margin required for the given stock symbols.  
  

## Request Attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`symbol`|string|The symbol in fyers symbology format for which margin is calculated. Example - "NSE:NIFTY2292217000CE"|
|`qty`|integer|The quantity of the particular stock. The quantity should be in multiples of lot size for derivatives.|
|`side`|integer|Calculate margin for buy or sell order. 1 => Buy, -1 => Sell|
|`type`|integer|1 => Limit Order 2 => Market Order 3 => Stop Order (SL-M) 4 => Stoplimit Order (SL-L) More details - [View Details](https://myapi.fyers.in/docsv3#tag/Order-Placement-Guide/Order-Types)|
|`productType`|string|The product type.The possible values are, 1) CNC 2) INTRADAY 3) MARGIN 4) CO 5) BO 6) MTF More details - [View Details](https://myapi.fyers.in/docsv3#tag/Order-Placement-Guide/Product-Types)|
|`limitPrice`|float|The limit price to calculate margin. (Keep default as 0.0)|
|`stopLoss`|float|Provide valid price to calculate margin for CO and BO orders. (Keep default as 0.0)|

### Request samples

- cURL

Copy

curl --location --request POST 'https://api.fyers.in/api/v2/span_margin' \ --header 'Authorization: UC0KMO****-102:eyJ0eX*****' \--header 'Content-Type: application/json' \ --data-raw '{
         "data": [{
           "symbol": "NSE:BANKNIFTY23NOV44400CE",
           "qty": 50,
           "side": -1,
           "type": 2,
           "productType": "INTRADAY",
           "limitPrice": 0.0,
           "stopLoss": 0.0
         }, {
           "symbol": "NSE:BANKNIFTY23NOVFUT",
           "qty": 50,
           "side": -1,
           "type": 2,
           "productType": "INTRADAY",
           "limitPrice": 0.0,
           "stopLoss": 0.0
           }]

## [](https://myapi.fyers.in/docsv3#tag/Margin-Calculator/paths/~1MarginCalculator/get)Multiorder Margin Calculator

Multiorder margin API will calculate the margin required for the given list of order bodies.  
  

## Request Attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`symbol`|string|The symbol in fyers symbology format for which margin is calculated. Example - "NSE:NIFTY2292217000CE"|
|`qty`|integer|The quantity of the particular stock. The quantity should be in multiples of lot size for derivatives.|
|`side`|integer|Calculate margin for buy or sell order. 1 => Buy, -1 => Sell|
|`type`|integer|1 => Limit Order 2 => Market Order 3 => Stop Order (SL-M) 4 => Stoplimit Order (SL-L) More details - [View Details](https://myapi.fyers.in/docsv3#tag/Order-Placement-Guide/Order-Types)|
|`productType`|string|The product type.The possible values are, 1) CNC 2) INTRADAY 3) MARGIN 4) CO 5) BO 6) MTF More details - [View Details](https://myapi.fyers.in/docsv3#tag/Order-Placement-Guide/Product-Types)|
|`limitPrice`|float|The limit price to calculate margin. (Keep default as 0.0)|
|`stopLoss`|float|Provide valid price to calculate margin for CO and BO orders.(Keep default as 0.0)|
|`stopPrice`|float|The stop price to calculate margin.(Keep default as 0.0) .(Keep default as 0.0)|
|`takeProfit`|float|Provide valid take profit price to calculate margin for CO and BO orders.(Keep default as 0.0)|

## Response attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`s`|string|ok / error|
|`code`|int|This is the code to identify specific responses|
|`margin_total`|float|Approximate margin required for the order.|
|`margin_new_order`|float|Approximate Total margin required including existing positions|
|`margin_avail`|float|Approximate available margin|

### Request samples

- cURL

Copy

curl --location --request POST 'https://api-t1.fyers.in/api/v3/multiorder/margin' \ --header 'Authorization: UC0KMO****-102:eyJ0eX*****' \--header 'Content-Type: application/json' \ --data-raw '{
  "data": [{
    "symbol": "NSE:NIFTY23DECFUT", 
    "qty": 50, 
    "side": 1, 
    "type": 2, 
    "productType": "MARGIN", 
    "limitPrice": 0.0, 
    "stopLoss": 0.0, 
    "stopPrice":0.0, 
    "takeProfit":0.0
  }, {
    "symbol": "NSE:SBIN-EQ", 
    "qty": 50, 
    "side": 1, 
    "type": 2, 
    "productType": "MARGIN", 
    "limitPrice": 0.0, 
    "stopLoss": 0.0, 
    "stopPrice":0.0, 
    "takeProfit":0.0
    }]
  ------------------------------------------------------------------------------------------------------------------------------------------
  Sample Success Response 
  ------------------------------------------------------------------------------------------------------------------------------------------
  { 
    "code": 200, 
    "message": "", 
    "data": { 
        "margin_avail": 1999.9, 
        "margin_total": 147738.05634886527, 
        "margin_new_order": 147738.05634886527 
    }, 
    "s": "ok" 
  } 

# [](https://myapi.fyers.in/docsv3#tag/Broker-Config)Broker Config

## [](https://myapi.fyers.in/docsv3#tag/Broker-Config/paths/~1Broker%20Config/post)Market Status

Fetches the current market status of all the exchanges and their segments

## Response attributes - For each exchange market segment

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`exchange`|int|The exchange in which the position is taken.  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Exchanges)|
|`segment`|int|The segment in which the position is taken.  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Segments)|
|`market_type`|string|NORMAL, ODD_LOT, CALL_AUCTION2, AUCTION|
|`status`|string|CLOSE  <br>OPEN  <br>POSTCLOSE_START  <br>POSTCLOSE_CLOSED  <br>PREOPEN  <br>PREOPEN_CLOSED|

### Request samples

- cURL
- python
- node
- Web modular API
- C#
- Java

Copy

Curl Request Method
curl -H "Authorization:app_id:access_token" https://api-t1.fyers.in/data/marketStatus

------------------------------------------------------------------------------------------------------------------------------------------
Sample Success Response 
------------------------------------------------------------------------------------------------------------------------------------------
{
  "code":200,
  "marketStatus":[
      {
        "exchange":10,
        "market_type":"NORMAL",
        "segment":10,
        "status":"POSTCLOSE_CLOSED"
      },
      {
        "exchange":10,
        "market_type":"NORMAL",
        "segment":11,
        "status":"CLOSED"
      },
      {
        "exchange":10,
        "market_type":"NORMAL",
        "segment":12,
        "status":"CLOSED"
      },
      {
        "exchange":10,
        "market_type":"CALL_AUCTION2",
        "segment":10,
        "status":"CLOSED"
      },
      {
        "exchange":10,
        "market_type":"AUCTION",
        "segment":10,
        "status":"CLOSED"
      },
      {
        "exchange":10,
        "market_type":"ODD_LOT",
        "segment":10,
        "status":"CLOSED"
      },
      {
        "exchange":11,
        "market_type":"NORMAL",
        "segment":20,
        "status":"OPEN"
      },
      {
        "exchange":11,
        "market_type":"SPECIAL",
        "segment":20,
        "status":"CLOSED"
      },
      {
        "exchange":12,
        "market_type":"NORMAL",
        "segment":10,
        "status":"POSTCLOSE_CLOSED"
      },
      {
        "exchange":12,
        "market_type":"NORMAL",
        "segment":12,
        "status":"POSTCLOSE_CLOSED"
      },
      {
        "exchange":12,
        "market_type":"AUCTION",
        "segment":10,
        "status":"CLOSED"
      },
      {
        "exchange":12,
        "market_type":"NORMAL",
        "segment":11,
        "status":"POSTCLOSE_CLOSED"
      }
  ],
  "message":"",
  "s":"ok"
}

## [](https://myapi.fyers.in/docsv3#tag/Broker-Config/paths/~1Broker%20Config/patch)Symbol Master

You can get all the latest symbols of all the exchanges from the symbol master files

- **NSE – Currency Derivatives:**  
    [https://public.fyers.in/sym_details/NSE_CD.csv](https://public.fyers.in/sym_details/NSE_CD.csv)
- **NSE – Equity Derivatives:**  
    [https://public.fyers.in/sym_details/NSE_FO.csv](https://public.fyers.in/sym_details/NSE_FO.csv)
- **NSE – Commodity:**  
    [https://public.fyers.in/sym_details/NSE_COM.csv](https://public.fyers.in/sym_details/NSE_COM.csv)
- **NSE – Capital Market:**  
    [https://public.fyers.in/sym_details/NSE_CM.csv](https://public.fyers.in/sym_details/NSE_CM.csv)
- **BSE – Capital Market:**  
    [https://public.fyers.in/sym_details/BSE_CM.csv](https://public.fyers.in/sym_details/BSE_CM.csv)
- **BSE - Equity Derivatives:**  
    [https://public.fyers.in/sym_details/BSE_FO.csv](https://public.fyers.in/sym_details/BSE_FO.csv)
- **MCX - Commodity:**  
    [https://public.fyers.in/sym_details/MCX_COM.csv](https://public.fyers.in/sym_details/MCX_COM.csv)

## File Headers

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`Fytoken`|string|Unique token for each symbol  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Fytoken)|
|`Symbol Details`|string|Name of the symbol|
|`Exchange Instrument type`|int|Exchange instrument type  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Exchanges)|
|`Minimum lot size`|int|Minimum qty multiplier|
|`Tick size`|float|Minimum price multiplier|
|`ISIN`|string|Unique ISIN provided by exchange for each symbol|
|`Trading Session`|string|Trading session provided in IST|
|`Last update date`|date|Date of last update|
|`Expiry date`|string|Date of expiry for a symbol.Applicable only for derivative contracts|
|`Symbol ticker`|string|Unique string to identify the symbol|
|`Exchange`|int|Exchange mapping  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Exchanges)|
|`Segment`|int|Segment of the symbol  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Segments)|
|`Scrip code`|int|Token of the Exchange|
|`Underlying symbol`|string|name of underlying symbol|
|`Underlying scrip code`|int|Scrip code of underlying symbol|
|`Strike price`|float|Strike price|
|`Option type`|string|CE/PE - For options  <br>XX - For other segments|
|`Underlying FyToken`|string|Unique token for the underlying symbol|
|`Reserved column`|string|Reserved for future, kindly ignore|
|`Reserved column`|int|Reserved for future, kindly ignore|
|`Reserved column`|float|Reserved for future, kindly ignore|

## [](https://myapi.fyers.in/docsv3#tag/Broker-Config/paths/~1Broker%20Config/put)Symbol Master Json

You can get all the latest symbols of all the exchanges from the symbol master json files

- **NSE – Currency Derivatives:**  
    [https://public.fyers.in/sym_details/NSE_CD_sym_master.json](https://public.fyers.in/sym_details/NSE_CD_sym_master.json)
- **NSE – Equity Derivatives:**  
    [https://public.fyers.in/sym_details/NSE_FO_sym_master.json](https://public.fyers.in/sym_details/NSE_FO_sym_master.json)
- **NSE – Commodity:**  
    [https://public.fyers.in/sym_details/NSE_COM_sym_master.json](https://public.fyers.in/sym_details/NSE_COM_sym_master.json)
- **NSE – Capital Market:**  
    [https://public.fyers.in/sym_details/NSE_CM_sym_master.json](https://public.fyers.in/sym_details/NSE_CM_sym_master.json)
- **BSE – Capital Market:**  
    [https://public.fyers.in/sym_details/BSE_CM_sym_master.json](https://public.fyers.in/sym_details/BSE_CM_sym_master.json)
- **BSE - Equity Derivatives:**  
    [https://public.fyers.in/sym_details/BSE_FO_sym_master.json](https://public.fyers.in/sym_details/BSE_FO_sym_master.json)
- **MCX - Commodity:**  
    [https://public.fyers.in/sym_details/MCX_COM_sym_master.json](https://public.fyers.in/sym_details/MCX_COM_sym_master.json)

## File Format

Key will be the symbol ticker and value will hold the below json object which has symbol master details for that particular symbol ticker.

|**Key**|**Data Type Of Values**|**Description**|
|---|---|---|
|`fyToken`|string|Unique token for the security  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Fytoken)|
|`isin`|string|ISIN code for the security|
|`exSymbol`|string|Exchange symbol of the security|
|`symDetails`|string|Full name of the security|
|`symTicker`|string|Unique string to identify the security|
|`exchange`|int|Exchange mapping  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Exchanges)|
|`segment`|int|Segment of the security  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Segments)|
|`exSymName`|string|Symbol name of the security|
|`exToken`|int|Exchange token|
|`exSeries`|string|Series of the security. This can be used only for CM segments|
|`optType`|string|CE/PE - For options  <br>XX - For others|
|`underSym`|string|name of underlying symbol|
|`underFyTok`|string|Unique token for the underlying symbol|
|`exInstType`|int|Exchange instrument type  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Instrument-Types)|
|`minLotSize`|int|Minimum qty multiplier|
|`tickSize`|float|Minimum price multiplier|
|`tradingSession`|string|Trading session provided in IST|
|`lastUpdate`|string|Date of last update in YYYY-MM-DD format|
|`expiryDate`|string|Date of expiry for a symbol in timestamp.Applicable only for derivative contracts|
|`strikePrice`|float|Strike price|
|`qtyFreeze`|string|Freeze qty  <br>Empty string in case value is not applicable|
|`tradeStatus`|int|Flag to check if security is allowed to trade.  <br>Expected values - 0/1  <br>1 = Active. 0 = Inactive.|
|`currencyCode`|string|Currency code|
|`upperPrice`|float|Upper circut price|
|`lowerPrice`|float|Lower circut price|
|`faceValue`|float|Face value|
|`qtyMultiplier`|float|Quantity multipler|
|`previousClose`|float|Previous close price|
|`previousOi`|float|Previous OI value|
|`asmGsmVal`|string|Surveillance Indicator message|
|`exchangeName`|string|Exchange Name  <br>NSE/BSE/MCX|
|`symbolDesc`|string|Full name of the security|
|`originalExpDate`|string|Kindly ignore this field|
|`is_mtf_tradable`|int|0: Not MTF tradable.  <br>1: MTF tradable.|
|`mtf_margin`|float|Indicates the margin multiplier available for MTF transactions.  <br>For example, a value of 2.9 means you receive 2.9x margin on the stock or security.|
|`stream`|string|Stream Group|

# [](https://myapi.fyers.in/docsv3#tag/EDIS)EDIS

Electronic Delivery Instruction Slip (eDIS) allows you to sell shares if your Power of Attorney (POA) is not submitted or DDPI is not activated.  
  
Please note: You can only sell the authorized stocks that you are holding in your Demat account. You can [activate DDPI](https://support.fyers.in/portal/en/kb/articles/how-do-i-activate-ddpi-for-my-account-on-fyers) to ensure a smooth and uninterrupted trading experience.

## [](https://myapi.fyers.in/docsv3#tag/EDIS/paths/~1EDIS/post)TPIN Generation

TPIN is an authorization code generated by CDSL/NSDL respectively, using which the customer validates/authorises the transaction.

### Request samples

- cURL

Copy

curl --location --request GET 'https://api.fyers.in/api/v2/tpin' 
--header 'Authorization: app_id:access_token'

------------------------------------------------------------------------------------------------------------------------------------------
Sample Success Response 
------------------------------------------------------------------------------------------------------------------------------------------
          
{"s": "ok", "code": 200, "message": "Successfully sent request for BO Tpin generation", "data": ""}

## [](https://myapi.fyers.in/docsv3#tag/EDIS/paths/~1EDIS/get)Details

This API provides information about holding authorizations that have been successfully completed.

### Request samples

- cURL

Copy

curl --location --request GET 'https://api.fyers.in/api/v2/details' \
 --header 'Authorization: app_id:access_token'

  ------------------------------------------------------------------------------------------------------------------------------------------
 Sample Success Response 
 ------------------------------------------------------------------------------------------------------------------------------------------
           
 {"s": "ok", "code": 200, "message": "", "data": [{"clientId": "DXXXX4", "isin": "INE313D01013", "qty": 1.0, "qtyUtlize": 0.0, "entryDate": "07/06/2021 13:58:56", "startDate": "07/06/2021", "endDate": "07/06/2021", "noOfDays": 1, "source": "W", "status": "SUCCESS", "reason": "eDIS Transaction done successfully", "internalTxnId": "915485", "dpTxnId": "0706202171316317", "errCode": "NA", "errorCount": "0", "transactionId": "915484108176"}]

## [](https://myapi.fyers.in/docsv3#tag/EDIS/paths/~1EDIS/put)Index

This Api will provide you with the CDSL page to login where you can submit your Holdings information and accordingly you can provide the same to exchange to Sell your holdings.

### Request samples

- cURL

Copy

curl --location --request POST 'https://api.fyers.in/api/v2/index' --header 'Authorization: app_id:accessToken' --header 'Content-Type: application/json' 
 --data-raw '{"recordLst": [{"isin_code": "INE114A01011","qty": "1","symbol": "NSE:SAIL-EQ"}]}'

  ------------------------------------------------------------------------------------------------------------------------------------------
 Sample Success Response 
 ------------------------------------------------------------------------------------------------------------------------------------------
           
  {"s": "ok", "code": 200, "message": "", "data": "<table width=\"100%\"><tr><td><table align=\"center\"><tr><td><table  align=\"center\"><tr><th><img src=\"https://clib.fyers.in/fy_images/320x132.png\" alt=\"Fyers\" width=\"220\" /></th></tr><tr style=\"color:#7c7e7f;\"><th class=\"sansserif\">&nbsp; &nbsp; &nbsp; Free Investment Zone</th></tr></table></td></tr></table><table align=\"center\" bgcolor=\"#ffffff\"  style=\"Margin: 0 auto;max-width: 600px;min-width: 320px; border-style:solid;border-left-width:10px;padding:5px; border-color:#ffffff;\"><tr style=\"color:#3e4751;\"><th><img src=\"https://mockedis.cdslindia.com/images/CDSL-Logo.png\"></th> </tr><tr><th><hr  style=\" border:1px solid\" width=\"12%\"><br></th></tr><br><tr align=\"left\" style=\"color:#7c7e7f;\"><td class=\"sansserif\" id=\"tpinDescp\">As per new regulations, clients are required to authorise sell transactions by providing specific instrument details along with quantites at the CDSL portal prior to executing any sell transactions from their demat account.<br><br> The autorisation will be valid till the end of the day irrespective of whether you have completed the sell transaction or not. <br><br></td></tr><tr align=\"left\" style=\"color:#7c7e7f;\"><td class=\"sansserif\"><br></td></tr><tr align=\"left\" style=\"color:#7c7e7f;\"><td class=\"sansserif\" style=\"text-align:center\"><br><br>       <form name= \"frmDIS\" method = \"post\" action= \"https://eDIS.cdslindia.com/eDIS/VerifyDIS\" >        <input type= \"hidden\" name= \"DPId\" value= \"89400\" />        <input type= \"hidden\" name= \"ReqId\" value= \"917177108176\" />        <input type= \"hidden\" name= \"Version\" value= \"1.1\" />        <input type= \"hidden\" name= \"TransDtls\" value= \"LD9WAIJCL2jgSj1hY2DABqfayzA6iInmBvh9ub+Ftqy0P+V/Qy4kRf9dsBHElVwcDdAhTx5a6+9g3y/TcVh1zEdMbslVXAcMi913u+YwHNp5IWUS6XAOCAx9UY01XZ+OVAgAez/9m+7cP6TjOeOBCqw57MWZ1y5N6OsPyzh+ecLUD2e6G5hJMc/ZKRw1dl5FvzJGpfmr1MGpM5jwtpzpbksmAIiAUMyx+zqfT5dX27ZLp0P4MRCl/QNyLnMCNwbhoPx7TEp6fN23UD8T3Y1742Kb1mVz3b4Aw6Kt+maXsjM12jP2bHZuM+rYKkjQWBK+AejT3Uk9vAZmFbd+Y1xeqKJFXAoKRA+cQXiCp8gjpm6RaZ04p8V7MMTWrIhpKAXNCCpCb+suxO74mjfW18AfZMKxX0UK/JjVomEoHz0GaIAKq4z3KAfwwcpqhtcNZv8u68DyeMmCFwojJ0Y+SBLjwUlJV3SWqpYhBnXxni5YsmvOK5NQLfWxd+KjuWK4gXgONgxWIcPMWsjY++JkYwtAlAhI43khxe0Y0SjntmZTZ4A=\" />        <input type= \"submit\" value=\"Submit\">         </form></td></tr><tr><td style=\"text-align: center;\" class=\"like-anchor\"><div id=\"forgetTpinDiv\"><a href=\"#\" id=\"forgetTpin\" onclick=\"tpin()\">Forgot CDSL TPIN</a></div></td></tr></tbody></table></td></tr></tbody></table>"}

## [](https://myapi.fyers.in/docsv3#tag/EDIS/paths/~1EDIS/delete)Inquiry

This Api is used to get the information/status of the provided transaction Id for the respective holdings you have on your end.  
**Note:** Transaction ID to be base64 encoded in payload. please refer to the [online tool](https://emn178.github.io/online-tools/base64_encode.html) for conversion.

### Request samples

- cURL

Copy

curl --location --request POST 'https://api.fyers.in/api/v2/inquiry' 
 --header 'Authorization: app_id:access_Token' --header 'Content-Type: application/json' --data-raw '{"transactionId": "OTE1NDg0MTA4MTc2"}'

  ------------------------------------------------------------------------------------------------------------------------------------------
 Sample Success Response 
 ------------------------------------------------------------------------------------------------------------------------------------------
           
  {"s": "ok", "code": 200, "message": "", "data": {"FAILED_CNT": 0, "SUCEESS_CNT": 1}}

# [](https://myapi.fyers.in/docsv3#tag/Postback-\(Webhooks\))Postback (Webhooks)

The Postback API sends a POST request with a JSON payload to the registered postback_url of your app when an order's status changes. This enables you to get orders updates reliably, irrespective of when they happen (Pending, Cancel, Rejected, Traded).

## [](https://myapi.fyers.in/docsv3#tag/Postback-\(Webhooks\)/1.-Create-web-hooks)1. Create web hooks

To Create Postback, you need to create an App by:

1. Login to [API Dashboard](https://myapi.fyers.in/dashboard/).
2. Once you have logged into the Dashboard, you will see a block where you need to update your webhook URL, webhook secret, and the webhook preference (Cancel, Rejected, Pending, Traded). Here you can add multiple webhooks by clicking on the "Add webhook" button. ![Create webhooks](https://assets.fyers.in/images/create-webhooks.png)
3. After entering the required details, click on the "Create App" button by accepting the terms and conditions.

## [](https://myapi.fyers.in/docsv3#tag/Postback-\(Webhooks\)/2.-Active-App)2. Active App

After successful creation of the App, you need to activate the App by following the Authentication & Login mechanism. After successfully logging in via the App, you will be able to get the order data over the webhook URL.

## [](https://myapi.fyers.in/docsv3#tag/Postback-\(Webhooks\)/3.-Response)3. Response

The JSON payload is posted as a raw HTTP POST body. You will have to read the raw body.

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|id|string|The unique order ID assigned for each order|
|exchOrdId|string|The order ID provided by the exchange|
|symbol|string|The symbol for which the order is placed|
|qty|int|The original order quantity|
|remainingQuantity|int|The remaining quantity|
|filledQty|int|The filled quantity after partial trades|
|status|int|1 => Canceled, 2 => Traded / Filled, 3 => (Not used currently), 4 => Transit, 5 => Rejected, 6 => Pending, 7 => Expired.|
|message|string|The error messages are shown here|
|segment|int|10 (Equity), 11 (F&O), 12 (Currency), 20 (Commodity). [View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Segments)|
|limitPrice|float|The limit price for the order|
|stopPrice|float|The stop price for the order|
|productType|string|The product type|
|type|int|1 => Limit Order, 2 => Market Order, 3 => Stop Order (SL-M), 4 => Stop Limit Order (SL-L). [View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Order-Types.)|
|side|int|Disclosed quantity: 1 => Buy, -1 => Sell. [View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Order-Sides)|
|disclosedQty|int|Disclosed quantity|
|dqQtyRem|int|Remaining disclosed quantity|
|orderValidity|string|DAY, IOC|
|orderDateTime|string|The datetime object here will be in epoch timestamp|
|tradedPrice|float|The average traded price for the order|
|source|string|Source from where the order was placed. [View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Order-Sources)|
|fytoken|string|Fytoken is a unique identifier for every symbol. [View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Fytoken)|
|offlineOrder|boolean|False => When the market is open, True => When placing AMO order|
|pan|string|PAN of the client|
|clientId|string|The client ID of the Fyers user|
|exchange|int|The exchange in which the order is placed. [View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Exchanges)|
|instrument|string|Exchange instrument type. [View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Instrument-Types)|

Response Output :

{
  "orderDateTime": "18-Jul-2023 11:44:29",
  "id": "23071800238607",
  "exchOrdId": "2500000061319029",
  "side": -1,
  "segment": 11,
  "instrument": 15,
  "productType": "MARGIN",
  "status": 2,
  "qty": 5400,
  "remainingQuantity": 0,
  "filledQty": 5400,
  "limitPrice": 2.15,
  "stopPrice": 0,
  "type": 2,
  "discloseQty": 0,
  "dqQtyRem": 0,
  "orderValidity": "DAY",
  "source": "M",
  "fyToken": "101123072754619",
  "offlineOrder": false,
  "message": "Completed",
  "orderNumStatus": "23071800238607:2",
  "tradedPrice": 2.15,
  "exchange": 10,
  "pan": "",
  "clientId": "xxxx",
  "symbol": "NSE:ABCAPITAL23JUL190CE"
}
  

## [](https://myapi.fyers.in/docsv3#tag/Postback-\(Webhooks\)/4.-Blacklisting)4. Blacklisting

The webhook/postback URL provided by the user can be blacklisted if the response status is not 200 from your web server or if the post request to your PostbackURL fails. These URLs are blacklisted for 30 minutes, and during that time, no webhooks are sent to the blacklisted URL. Additionally, the URL will be blacklisted after continuous failures, typically after three retries.

# [](https://myapi.fyers.in/docsv3#tag/Data-Api)Data Api

## [](https://myapi.fyers.in/docsv3#tag/Data-Api/paths/~1DataApi/post)History

The historical API provides archived data (up to date) for the symbols. across various exchanges within the given range. A historical record is presented in the form of a candle and the data is available in different resolutions like - minute, 10 minutes, 60 minutes...240 minutes and daily.

  
**To Handle partial Candle**  

To receive completed candle data, it is important to send a timestamp that comes before the current minute. If you send a timestamp for the current minute, you will receive partial data because the minute is not yet finished. Therefore, it is recommended to always use a "range_to" timestamp of the previous minute to ensure that you receive the completed candle data.

**Example:**

Current Time(seconds can be 1-59): 12:10:20 PM

Input for history will be:

- range_from: 12:08:00 PM
- range_to: Current Time - 1 minute = 12:09:20 PM

So you will get 2 candles - 12:08 PM and 12:09 PM candles. This example is for 1-minute candles; for other resolutions, you have to subtract the resolution time from "range_to" to get completed candles only.

  
**Limits for History**  

- Unlimited number of stocks history data can be downloaded in a day.
- Up to 100 days of data per request for resolutions of 1, 2, 3, 5, 10, 15, 20, 30, 45, 60, 120, 180, and 240 minutes. Data is available from July 3, 2017.
- For 1D resolutions up to 366 days of data per request for 1D (1 day) resolutions.
- For Seconds Charts the history will be available only for 30-Trading Days

## Request Attribute

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`symbol*`|string|Mandatory.  <br>Eg: NSE:SBIN-EQ|
|`resolution*`|string|The candle resolution. Possible values are: Day : “D” or “1D”  <br>5 seconds : “5S”  <br>10 seconds : “10S”  <br>15 seconds : “15S”  <br>30 seconds : “30S”  <br>45 seconds : “45S”  <br>1 minute : “1”  <br>2 minute : “2"  <br>3 minute : "3"  <br>5 minute : "5"  <br>10 minute : "10"  <br>15 minute : "15"  <br>20 minute : "20"  <br>30 minute : "30"  <br>60 minute : "60"  <br>120 minute : "120"  <br>240 minute : "240"|
|`date_format*`|int|date_format is a boolean flag. 0 to enter the epoch value. Eg:670073472. 1 to enter the date format as yyyy-mm-dd.|
|`range_from*`|string|Indicating the start date of records. Accepts epoch value if date_format flag is set to 0. Eg: range_from: 670073472  <br>Accepts yyyy-mm-dd format if date_format flag is set to 1. Eg: 2021-01-01|
|`range_to*`|string|Indicating the end date of records. Accepts epoch value if date_format flag is set to 0. Eg: range_to: 1622028732  <br>Accepts yyyy-mm-dd format if date_format flag is set to 1. Eg:2021-03-01|
|`cont_flag*`|int|set cont flag 1 for continues data and future options.|
|`oi_flag`|int|set flag to "1" enable oi as a part of candle.|

## Response Attribute

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`s`|string|ok / error|
|`Candels`|array|Candles data containing array of following data for particular time stamp:  <br>1.Current epoch time  <br>2. Open Value  <br>3.Highest Value  <br>4.Lowest Value  <br>5.Close Value  <br>6.Total traded quantity (volume)|

### Request samples

- cURL
- Python
- Node
- Web modular API
- C#
- Java

Copy

curl --location --request GET 'https://api-t1.fyers.in/data/history?symbol=NSE:SBIN-EQ&resolution=30&date_format=1&range_from=2021-01-01&range_to=2021-01-02&cont_flag=' \
 --header 'Authorization:app_id:access_token’

 ------------------------------------------------------------------------------------------------------------------------------------------
 Sample Success Response 
 ------------------------------------------------------------------------------------------------------------------------------------------
 {
   "s": "ok",
   "candles": [
       [
           1621814400,
           417.0,
           419.2,
           405.3,
           412.05,
           142964052
       ],
       [
           1621900800,
           415.1,
           415.5,
           408.5,
           412.35,
           56048127
       ],
       [
           1621987200,
           413.8,
           418.75,
           410.8,
           413.55,
           52357719
       ],
       [
           1622073600,
           413.7,
           429.1,
           412.0,
           425.2,
           73392997
       ]
   ]
 }

## [](https://myapi.fyers.in/docsv3#tag/Data-Api/paths/~1DataApi/get)Quotes

The Quotes API retrieves the full market quotes for one or more symbols provided by the user.

## Request attributes

|**Attribute**|**Data Type**|*_Description_|
|---|---|---|
|`symbols*`|string|Maximum symbol limit is 50. Eg: NSE:SBIN-EQ.|

## Response attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`s`|string|ok / error|
|`ch`|float|Change value|
|`chp`|float|Percentage of change between the current value and the previous day's market close|
|`lp`|float|Last traded price|
|`spread`|float|Difference between lowest asking and highest bidding price|
|`ask`|float|Asking price for the symbol|
|`bid`|float|Bidding price for the symbol|
|`open_price`|float|Price at market opening time|
|`high_price`|float|Highest price for the day|
|`low_price`|float|Lowest price for the day|
|`prev_close_price`|float|Previous closing price|
|`atp`|float|Average traded price|
|`volume`|int|Volume traded|
|`short_name`|string|Short name for the symbol Eg: “SBIN-EQ”|
|`exchange`|string|Name of the exchange. Eg: “NSE” or “BSE”|
|`description`|string|Description of the symbol|
|`original_name`|string|Original name of the symbol name provided by the use|
|`symbol`|string|Symbol name provided by the user|
|`fyToken`|string|Unique token for each symbol|
|`tt`|int|Today’s time|
|`cmd`|dict|---Deprecated---|

### Request samples

- cURL
- Python
- Node
- Web modular API
- C#
- Java

Copy

curl --location --request GET 'https://api-t1.fyers.in/data/quotes?symbols=NSE:SBIN-EQ' \
 --header 'Authorization: app_id:access_token’

 ------------------------------------------------------------------------------------------------------------------------------------------
 Sample Success Response 
 ------------------------------------------------------------------------------------------------------------------------------------------
 {
 "s": "ok",
 "code": 200,
 "d": [
     {
         "n": "NSE:SBIN-EQ",
         "s": "ok",
         "v": {
             "ch": 1.7,
             "chp": 0.4,
             "lp": 426.9,
             "spread": 0.05,
             "ask": 426.9,
             "bid": 426.85,
             "open_price": 430.5,
             "high_price": 433.65,
             "low_price": 423.6,
             "prev_close_price": 425.2,
             "atp": 428.07,
             "volume": 38977242,
             "short_name": "SBIN-EQ",
             "exchange": "NSE",
             "description": "NSE:SBIN-EQ",
             "original_name": "NSE:SBIN-EQ",
             "symbol": "NSE:SBIN-EQ",
             "fyToken": "10100000003045",
             "tt": "1622160000",
                 }
           }
                 ]
           }

## [](https://myapi.fyers.in/docsv3#tag/Data-Api/paths/~1DataApi/put)Market Depth

The Market Depth API returns the complete market data of the symbol provided. It will include the quantity, OHLC values, and Open Interest fields, and bid/ask prices.

## Request attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`symbol*`|string|Mandatory.  <br>Eg: NSE:SBIN-EQ|
|`ohlcv_flag*`|int|Set the ohlcv_flag to 1 to get open, high, low, closing and volume quantity'|

## Response attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`s`|string|ok / error|
|`code`|int|This is the code to identify specific responses|
|`totalbuyqty`|int|Total buying quantity|
|`totalsellqty`|int|Total selling quantity|
|`bids`|array|Bidding price along with volume and total number of orders|
|`ask`|array|Offer price with volume and total number of orders|
|`o`|float|Price at market opening time|
|`h`|float|Highest price for the day|
|`i`|float|Lowest price for the day|
|`c`|float|Price at the of market closing|
|`chp`|float|Percentage of change between the current value and the previous day's market close|
|`tick_Size`|float|Minimum price multiplier|
|`ch`|float|Change value|
|`ltq`|int|Last traded quantity|
|`ltt`|int|Last traded time|
|`ltp`|float|Last traded price|
|`v`|int|Volume traded|
|`atp`|float|Average traded price|
|`lower_ckt`|float|Lower circuit price`|
|`upper_ckt`|float|upper circuit price|
|`expiry`|string|Expiry date|
|`oi`|float|Open interest|
|`oiflag`|bool|Boolean flag for OI data, true or false|
|`pdoi`|int|previous day open interest|
|`oipercent`|float|Change in open Interest percentage|

### Request samples

- cURL
- Python
- Node
- Web modular API
- C#
- Java

Copy

curl --location --request GET 'https://api-t1.fyers.in/data/depth?symbol=NSE:SBIN-EQ&ohlcv_flag=1' \
--header 'Authorization:app_id:access_token’

 ------------------------------------------------------------------------------------------------------------------------------------------
 Sample Success Response 
 ------------------------------------------------------------------------------------------------------------------------------------------
 {
 "s": "ok",
 "d": {
     "NSE:SBIN-EQ": {
         "totalbuyqty": 2396063,
         "totalsellqty": 4990001,
         "bids": [
             {
                 "price": 427.25,
                 "volume": 4738,
                 "ord": 5
             },
             {
                 "price": 427.2,
                 "volume": 2631,
                 "ord": 9
             },
             {
                 "price": 427.15,
                 "volume": 6366,
                 "ord": 19
             },
             {
                 "price": 427.1,
                 "volume": 6344,
                 "ord": 18
             },
             {
                 "price": 427.05,
                 "volume": 8136,
                 "ord": 16
             }
         ],
         "ask": [
             {
                 "price": 427.4,
                 "volume": 2193,
                 "ord": 4
             },
             {
                 "price": 427.45,
                 "volume": 5406,
                 "ord": 19
             },
             {
                 "price": 427.5,
                 "volume": 15311,
                 "ord": 57
             },
             {
                 "price": 427.55,
                 "volume": 11170,
                 "ord": 17
             },
             {
                 "price": 427.6,
                 "volume": 7272,
                 "ord": 25
             }
         ],
         "o": 430.5,
         "h": 433.65,
         "l": 423.6,
         "c": 425.2,
         "chp": 0.48,
         "tick_Size": 0.05,
         "ch": 2.05,
         "ltq": 20,
         "ltt": 1622184920,
         "ltp": 427.25,
         "v": 39163870,
         "atp": 428.07,
         "lower_ckt": 382.7,
         "upper_ckt": 467.7,
         "expiry": "",
         "oi": 0,
         "oiflag": false,
         "pdoi": 0,
         "oipercent": 0.0
     }
 },
  "message": ""
  }

## [](https://myapi.fyers.in/docsv3#tag/Data-Api/paths/~1DataApi/delete)Option Chain

The Optionchain API provides important information about options trading, specifically focusing on strike prices, which are predetermined prices at which an option contract can be exercised. This API offers data for both Call (CE) and Put (PE) options, along with values for index, IndiaVIX (Volatility Index) and available expiry dates. When using the API, you can specify the number of strike prices you're interested in. For example, if you request a strike count of 2, the API will return data for:

- **At-The-Money (ATM) strike:** The closest strike price to the current market price.
- **Out-of-The-Money (OTM) strikes:** Strike prices higher than the current market price for Calls (CE) and lower than the current market price for Puts (PE). The API will return data for 2 CE and 2 PE OTM strikes.
- **In-The-Money (ITM) strikes:** Strike prices lower than the current market price for Calls (CE) and higher than the current market price for Puts (PE). The API will return data for 2 CE and 2 PE ITM strikes.

.

## Request attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`symbol*`|string|Mandatory.  <br>Eg: NSE:SBIN-EQ|
|`strikecount`|int|Options strike count for symbol(MAX = 50)|
|`timestamp`|string|Options chain data at timestamp'|

## Response attributes

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`s`|string|ok / error|
|`code`|int|This is the code to identify specific responses|
|`callOi`|int|Total open interest for call options|
|`putOi`|int|Total open interest for put options|
|`date`|string|Expiry date in DD-MM-YYYY|
|`expiry`|string|Expiry timestamp|
|`ask`|float|Ask price|
|`bid`|float|Bid price|
|`description`|string|Description of the stock|
|`ex_symbol`|string|Exchange Symbol|
|`exchange`|int|The exchange in which order is placed.  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Exchanges)|
|`fytoken`|string|Fytoken is a unique identifier for every symbol.  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Fytoken)|
|`ltp`|float|LTP is the price from which the next sale of the stocks happens|
|`ltpch`|float|Change in last traded price|
|`ltpchp`|float|Percentage change in last traded price|
|`option_type`|string|Type of option (if applicable)|
|`strike_price`|int|Strike price (if applicable)|
|`symbol`|string|Symbol|
|`fp`|float|Future price|
|`fpch`|float|Change in future price|
|`fpchp`|float|Percentage change in future price|
|`oi`|int|Open interest|
|`oich`|int|Change in Open interest|
|`oichp`|float|Percentage change in Open interest|
|`prev_oi`|int|Previous Open interest|
|`volume`|int|Volume traded|

### Request samples

- cURL
- Python
- Node
- Web modular API
- C#
- Java

Copy

curl --location 'https://api-t1.fyers.in/data/options-chain-v3?symbol=NSE%3ATCS-EQ&strikecount=1' \
--header 'Authorization: access token' \
 ------------------------------------------------------------------------------------------------------------------------------------------
 Sample Success Response 
 ------------------------------------------------------------------------------------------------------------------------------------------
 {
  "code": 200,
  "data": {
      "callOi": 9926700,
      "expiryData": [
          {
              "date": "25-04-2024",
              "expiry": "1714039200"
          },
          {
              "date": "30-05-2024",
              "expiry": "1717063200"
          },
          {
              "date": "27-06-2024",
              "expiry": "1719482400"
          }
      ],
      "indiavixData": {
          "ask": 0,
          "bid": 0,
          "description": "INDIAVIX-INDEX",
          "ex_symbol": "INDIAVIX",
          "exchange": "NSE",
          "fyToken": "101000000026017",
          "ltp": 10.34,
          "ltpch": -2.36,
          "ltpchp": -18.58,
          "option_type": "",
          "strike_price": -1,
          "symbol": "NSE:INDIAVIX-INDEX"
      },
      "optionsChain": [
          {
              "ask": 3889.2,
              "bid": 3889.1,
              "description": "TATA CONSULTANCY SERV LT",
              "ex_symbol": "TCS",
              "exchange": "NSE",
              "fp": 3884.1,
              "fpch": 21.65,
              "fpchp": 0.56,
              "fyToken": "101000000011536",
              "ltp": 3889.2,
              "ltpch": 24.6,
              "ltpchp": 0.64,
              "option_type": "",
              "strike_price": -1,
              "symbol": "NSE:TCS-EQ"
          },
          {
              "ask": 40.35,
              "bid": 39.55,
              "fyToken": "1011240425139431",
              "ltp": 40.5,
              "ltpch": 8.4,
              "ltpchp": 26.17,
              "oi": 93275,
              "oich": -9625,
              "oichp": -9.35,
              "option_type": "CE",
              "prev_oi": 102900,
              "strike_price": 3860,
              "symbol": "NSE:TCS24APR3860CE",
              "volume": 229950
          },
          {
              "ask": 15.85,
              "bid": 15.65,
              "fyToken": "1011240425139432",
              "ltp": 15.55,
              "ltpch": -15.9,
              "ltpchp": -50.56,
              "oi": 162225,
              "oich": 31675,
              "oichp": 24.26,
              "option_type": "PE",
              "prev_oi": 130550,
              "strike_price": 3860,
              "symbol": "NSE:TCS24APR3860PE",
              "volume": 347900
          },
          {
              "ask": 28.8,
              "bid": 28.45,
              "fyToken": "1011240425133432",
              "ltp": 28.75,
              "ltpch": 3.25,
              "ltpchp": 12.75,
              "oi": 162225,
              "oich": 6300,
              "oichp": 4.04,
              "option_type": "CE",
              "prev_oi": 155925,
              "strike_price": 3880,
              "symbol": "NSE:TCS24APR3880CE",
              "volume": 606200
          },
          {
              "ask": 24.85,
              "bid": 24.5,
              "fyToken": "1011240425133433",
              "ltp": 24.9,
              "ltpch": -18.4,
              "ltpchp": -42.49,
              "oi": 102550,
              "oich": 32725,
              "oichp": 46.87,
              "option_type": "PE",
              "prev_oi": 69825,
              "strike_price": 3880,
              "symbol": "NSE:TCS24APR3880PE",
              "volume": 223650
          },
          {
              "ask": 21,
              "bid": 20.85,
              "fyToken": "1011240425139433",
              "ltp": 21.1,
              "ltpch": 1.95,
              "ltpchp": 10.18,
              "oi": 614775,
              "oich": 7000,
              "oichp": 1.15,
              "option_type": "CE",
              "prev_oi": 607775,
              "strike_price": 3900,
              "symbol": "NSE:TCS24APR3900CE",
              "volume": 1166375
          },
          {
              "ask": 36.5,
              "bid": 36.05,
              "fyToken": "1011240425139434",
              "ltp": 35.7,
              "ltpch": -20.7,
              "ltpchp": -36.7,
              "oi": 344225,
              "oich": -3850,
              "oichp": -1.11,
              "option_type": "PE",
              "prev_oi": 348075,
              "strike_price": 3900,
              "symbol": "NSE:TCS24APR3900PE",
              "volume": 158900
          }
      ],
      "putOi": 3789100
  },
  "message": "",
  "s": "ok"
}

# [](https://myapi.fyers.in/docsv3#tag/Web-Socket)Web Socket

## [](https://myapi.fyers.in/docsv3#tag/Web-Socket/paths/~1GeneralSocket/head)Introduction

The WebSocket provides a robust method for accessing real-time data or order updates seamlessly and with low latency. It enables developers and users to establish a persistent, bidirectional connection with the server, allowing them to receive continuous updates, such as symbol updates, depth updates or orderupdate. To enhance your experience with our WebSocket, here are some helpful tips and best practices

1. **Subscription Limit:** You have the flexibility to subscribe up to **5000** data subscriptions simultaneously via WebSocket with latest SDK versions, please refer [Change Log](https://myapi.fyers.in/docsv3#tag/Change-Log). Staying within this limit ensures smooth subscription management without errors.
2. **Single Instance:** Keep in mind that you can create only one WebSocket connection instance at a time. This approach ensures stability and prevents issues that might arise from multiple concurrent connections.
3. **Efficient Thread Management:** WebSocket operates on a dedicated thread, allowing it to run independently of your main application thread. This design guarantees that your primary tasks can continue without interruptions from WebSocket operations.
4. **Customizable Callback Functions:** Tailor your application's behavior using callback functions provided by the WebSocket. These functions empower you to define specific actions for events like data updates or error occurrences.
5. **Auto-Reconnect:** Enjoy uninterrupted connectivity by enabling automatic reconnection in case of disconnection. Simply set the reconnect parameter to true during WebSocket initialization, ensuring your application can recover without manual intervention.You can set max reconnection count upto 50.
6. **Logging to File:** If you want to log data to a file, you can set the write_to_file parameter to true. This feature allows you to efficiently save received data to a log file for analysis or archival purposes. The write_to_file function will only work without callback functions.
7. **Reconnect Retry:** If you want to define dynamic retry count(max 50), you can set the reconnect_retry parameter to int value of number of times you want it to try reconnection.(In case of node `fyersdata.autoreconnect(trycount)`)
8. **Disable Logging(node JS):** In case you want to disable logging use disable logging flag to disable logging sample format:  
    `new FyersSocket("token","logpath",true/*flag to enable disable logging*/)`

### Request samples

- Python
- Node
- C#
- Java

Copy

from fyers_apiv3.FyersWebsocket import data_ws

fyers = data_ws.FyersDataSocket(
    access_token=access_token,       # Access token in the format "appid:accesstoken"
    log_path="",                     # Path to save logs. Leave empty to auto-create logs in the current directory.
    litemode=False,                  # Lite mode disabled. Set to True if you want a lite response.
    write_to_file=False,              # Save response in a log file instead of printing it.
    reconnect=True,                  # Enable auto-reconnection to WebSocket on disconnection.
    on_connect=onopen,               # Callback function to subscribe to data upon connection.
    on_close=onclose,                # Callback function to handle WebSocket connection close events.
    on_error=onerror,                # Callback function to handle WebSocket errors.
    on_message=onmessage,            # Callback function to handle incoming messages from the WebSocket.
    reconnect_retry=10               # Number of times reconnection will be attepmted in case
)

## [](https://myapi.fyers.in/docsv3#tag/Web-Socket/paths/~1GeneralSocket/post)General Socket (orders)

The WebSocket API for receiving order, position, trade, price alerts, and EDIS updates is a real-time communication protocol designed to provide seamless access to various critical elements of a trading and EDIS system. This API allows traders and developers to establish a persistent, bidirectional connection with the server, enabling them to receive real-time updates on their orders, current positions, executed trades, price alerts, and EDIS status.

## Response attributes - For order updates

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`id`|string|The unique order id assigned for each order|
|`exchOrdId`|string|The order id provided by the exchange|
|`symbol`|string|The symbol for which order is placed|
|`qty`|int|The original order qty|
|`remainingQuantity`|int|The remaining qty|
|`filledQty`|int|The filled qty after partial trades|
|`status`|int|- 1 => Canceled<br>- 2 => Traded / Filled<br>- 3 => (Not used currently)<br>- 4 => Transit<br>- 5 => Rejected<br>- 6 => Pending<br>- 7 => Expired<br>- [View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Order-Status)|
|`message`|string|The error messages are shown here|
|`segment`|int|- 10 => E (Equity)<br>- 11 => D (F&O)<br>- 12 => C (Currency)<br>- 20 => M (Commodity)<br>- [View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Segments)|
|`limitPrice`|float|The limit price for the order|
|`stopPrice`|float|The limit price for the order|
|`productType`|string|The product type|
|`type`|int|- 1 => Limit Order<br>- 2 => Market Order<br>- 3 => Stop Order (SL-M)<br>- 4 => Stoplimit Order (SL-L)|
|`side`|int|- 1 => Buy<br>- -1 => Sell<br>- [View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Order-Sides)|
|`orderValidity`|string|- DAY<br>- IOC|
|`orderDateTime`|string|The order time as per DD-MMM-YYYY hh:mm:ss in IST|
|`parentId`|string|The parent order id will be provided only for applicable orders..  <br>Eg: BO Leg 2 & 3 and CO Leg 2|
|`tradedPrice`|float|The average traded price for the order|
|`source`|string|Source from where the order was placed.  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Order-Sources)|
|`fytoken`|string|Fytoken is a unique identifier for every symbol.  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Fytoken)|
|`offlineOrder`|boolean|- False => When market is open<br>- True => When placing AMO order|
|`pan`|string|PAN of the client|
|`clientId`|string|The client id of the fyers user|
|`exchange`|int|The exchange in which order is placed  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Exchanges)|
|`instrument`|int|Exchange instrument type  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Instrument-Types)|

### Request samples

- Python
- Node
- Web modular API
- C#
- Java

Copy

from fyers_apiv3.FyersWebsocket import order_ws

def onOrder(message):
    """
    Callback function to handle incoming messages from the FyersDataSocket WebSocket.

    Parameters:
        message (dict): The received message from the WebSocket.

    """
    print("Order Response:", message)

def onerror(message):
    """
    Callback function to handle WebSocket errors.

    Parameters:
        message (dict): The error message received from the WebSocket.

    """
    print("Error:", message)

def onclose(message):
    """
    Callback function to handle WebSocket connection close events.
    """
    print("Connection closed:", message)

def onopen():
    """
    Callback function to subscribe to data type and symbols upon WebSocket connection.

    """
    # Specify the data type and symbols you want to subscribe to
    data_type = "OnOrders"
    # data_type = "OnTrades"
    # data_type = "OnPositions"
    # data_type = "OnGeneral"
    # data_type = "OnOrders,OnTrades,OnPositions,OnGeneral"

    fyers.subscribe(data_type=data_type)

    # Keep the socket running to receive real-time data
    fyers.keep_running()

# Replace the sample access token with your actual access token obtained from Fyers
access_token = "Xxxxx67IM-100:eyJxxxxxxIUzI1NiJ9.eyJpc3MiOiJhcGkuZnllcnMuaW4iLCJpYXQiOjE2OTA5NTMyNjAsImV4cCI6MTY5MTAyMjYyMCwibmJmIjoxNjkwOTUzMjYwLCJhdWQiOlsieDowIiwieDoxIiwieDoyIiwiZDoxIiwiZDoyIiwieDoxIiwieDowIl0sInN1YiI6ImFjY2Vzc190b2tlbiIsImF0X2hhc2giOiJnQUFBQUFCa3llWXMtX1FSSVdRLUItcUxENUdodFMxZ3JjeTZvREhSbjJhNE5EUEN2TWJLSEc1UEtaM3NqNWE5YWNzNDVueDQ1dHhkeWpqS1lNU1VTTmp2eDhfMlppXzNHQ2pJVkxDcE14U1BLUlhRTkFYV29xYz0iLCJkaXNwbGF5X25hbWUiOiJWSU5BWSBLVU1BUiBNQVVSWUEiLCJvbXMiOiJLMSIsImhzbV9rZXkiOiIwYTU1NjU0ZGE5ZGM4NTMxMTFjN2FjMjQ2MzZlOTI1NDExMTBiN2M1MmNjNWNiZDE0MDA2OTA1NyIsImZ5X2lkIjoiWFYyMDk4NiIsImFwcFR5cGUiOjEwMCwicG9hX2ZsYWciOiJOIn0.vDp4UV_JIPxxxxGXLQOT7NnGxxxxNSBoLo"

# Create a FyersDataSocket instance with the provided parameters
fyers = order_ws.FyersOrderSocket(
    access_token=access_token,  # Your access token for authenticating with the Fyers API.
    write_to_file=False,        # A boolean flag indicating whether to write data to a log file or not.
    log_path="",                # The path to the log file if write_to_file is set to True (empty string means current directory).
    on_connect=onopen,          # Callback function to be executed upon successful WebSocket connection.
    on_close=onclose,           # Callback function to be executed when the WebSocket connection is closed.
    on_error=onerror,           # Callback function to handle any WebSocket errors that may occur.
    on_orders=onOrder,          # Callback function to handle order-related events from the WebSocket.
)

# Establish a connection to the Fyers WebSocket
fyers.connect()

------------------------------------------------------------------------------------------------------------------------------------------
Sample Success Response 
------------------------------------------------------------------------------------------------------------------------------------------
                      
{
  "s":"ok",
  "orders":{
      "clientId":"XV20986",
      "id":"23080400089344",
      "exchOrdId":"1100000009596016",
      "qty":1,
      "filledQty":1,
      "limitPrice":7.95,
      "type":2,
      "fyToken":"101000000014366",
      "exchange":10,
      "segment":10,
      "symbol":"NSE:IDEA-EQ",
      "instrument":0,
      "offlineOrder":false,
      "orderDateTime":"04-Aug-2023 10:12:58",
      "orderValidity":"DAY",
      "productType":"INTRADAY",
      "side":-1,
      "status":90,
      "source":"W",
      "ex_sym":"IDEA",
      "description":"VODAFONE IDEA LIMITED",
      "orderNumStatus":"23080400089344:2"
  }
}

## [](https://myapi.fyers.in/docsv3#tag/Web-Socket/paths/~1GeneralSocket/get)General Socket (trades)

## Response attributes - For trade update

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`symbol`|string|Eg: NSE:SBIN-EQ|
|`id`|string|The unique id to sort the trades|
|`orderDateTime`|string|The time when the trade occured in “DD-MM-YYYY hh:mm:ss” format in IST|
|`orderNumber`|string|The order id for which the trade occurred|
|`tradeNumber`|string|The trade number generated by the exchange|
|`tradePrice`|float|The traded price|
|`tradeValue`|float|The total traded value|
|`tradedQty`|int|The total traded qty|
|`side`|int|- 1 => Buy<br>- -1 => Sell<br>- [View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Order-Sides)|
|`productType`|string|The product in which the order was placed  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Product-Types.)|
|`exchangeOrderNo`|string|The order number provided by the exchange|
|`segment`|int|The segment in which order is placed  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Segments)|
|`exchange`|int|The exchange in which order is placed  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Exchanges)|
|`fyToken`|string|Fytoken is a unique identifier for every symbol.|

### Request samples

- Python
- Node
- Web modular API
- C#
- Java

Copy

from fyers_apiv3.FyersWebsocket import order_ws

def onTrade(message):
    """
    Callback function to handle incoming messages from the FyersDataSocket WebSocket.

    Parameters:
        message (dict): The received message from the WebSocket.

    """
    print("Trade Response:", message)

def onerror(message):
    """
    Callback function to handle WebSocket errors.

    Parameters:
        message (dict): The error message received from the WebSocket.


    """
    print("Error:", message)

def onclose(message):
    """
    Callback function to handle WebSocket connection close events.
    """
    print("Connection closed:", message)

def onopen():
    """
    Callback function to subscribe to data type and symbols upon WebSocket connection.

    """
    # Specify the data type and symbols you want to subscribe to
    data_type = "OnTrades"

    # data_type = "OnOrders"
    # data_type = "OnPositions"
    # data_type = "OnGeneral"
    # data_type = "OnOrders,OnTrades,OnPositions,OnGeneral"

    fyers.subscribe(data_type=data_type)

    # Keep the socket running to receive real-time data
    fyers.keep_running()

# Replace the sample access token with your actual access token obtained from Fyers
access_token = "Xxxxx67IM-100:eyJxxxxxxIUzI1NiJ9.eyJpc3MiOiJhcGkuZnllcnMuaW4iLCJpYXQiOjE2OTA5NTMyNjAsImV4cCI6MTY5MTAyMjYyMCwibmJmIjoxNjkwOTUzMjYwLCJhdWQiOlsieDowIiwieDoxIiwieDoyIiwiZDoxIiwiZDoyIiwieDoxIiwieDowIl0sInN1YiI6ImFjY2Vzc190b2tlbiIsImF0X2hhc2giOiJnQUFBQUFCa3llWXMtX1FSSVdRLUItcUxENUdodFMxZ3JjeTZvREhSbjJhNE5EUEN2TWJLSEc1UEtaM3NqNWE5YWNzNDVueDQ1dHhkeWpqS1lNU1VTTmp2eDhfMlppXzNHQ2pJVkxDcE14U1BLUlhRTkFYV29xYz0iLCJkaXNwbGF5X25hbWUiOiJWSU5BWSBLVU1BUiBNQVVSWUEiLCJvbXMiOiJLMSIsImhzbV9rZXkiOiIwYTU1NjU0ZGE5ZGM4NTMxMTFjN2FjMjQ2MzZlOTI1NDExMTBiN2M1MmNjNWNiZDE0MDA2OTA1NyIsImZ5X2lkIjoiWFYyMDk4NiIsImFwcFR5cGUiOjEwMCwicG9hX2ZsYWciOiJOIn0.vDp4UV_JIPxxxxGXLQOT7NnGxxxxNSBoLo"

# Create a FyersDataSocket instance with the provided parameters
fyers = order_ws.FyersOrderSocket(
    access_token=access_token,  # Your access token for authenticating with the Fyers API.
    write_to_file=False,        # A boolean flag indicating whether to write data to a log file or not.
    log_path="",                # The path to the log file if write_to_file is set to True (empty string means current directory).
    on_connect=onopen,          # Callback function to be executed upon successful WebSocket connection.
    on_close=onclose,           # Callback function to be executed when the WebSocket connection is closed.
    on_error=onerror,           # Callback function to handle any WebSocket errors that may occur.
    on_trades=onTrade           # Callback function to handle trade-related events from the WebSocket.
)

# Establish a connection to the Fyers WebSocket
fyers.connect()

------------------------------------------------------------------------------------------------------------------------------------------
Sample Success Response 
------------------------------------------------------------------------------------------------------------------------------------------
  {
    "s":"ok",
    "trades":{
        "tradeNumber":"23080400089344-21726639",
        "orderNumber":"23080400089344",
        "tradedQty":1,
        "tradePrice":7.95,
        "tradeValue":7.95,
        "productType":"INTRADAY",
        "clientId":"XV20986",
        "exchangeOrderNo":"1100000009596016",
        "orderType":2,
        "side":-1,
        "symbol":"NSE:IDEA-EQ",
        "orderDateTime":"04-08-2023 10:12:58",
        "fyToken":"101000000014366",
        "exchange":10,
        "segment":10
    }
  }

## [](https://myapi.fyers.in/docsv3#tag/Web-Socket/paths/~1GeneralSocket/put)General Socket (positions)

## Response attributes - For position updates

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`symbol`|string|Eg: NSE:SBIN-EQ|
|`id`|string|The unique value for each position|
|`buyAvg`|float|Average buy price|
|`buyQty`|int|Total buy qty|
|`sellAvg`|float|Average sell price|
|`sellQty`|int|Total sell qty|
|`netAvg`|float|netAvg|
|`netQty`|int|Net qty|
|`side`|int|The side shows whether the position is long / short  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Position-Sides)|
|`qty`|int|Absolute value of net qty|
|`productType`|string|The product type of the position  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Product-Types.)|
|`realized_profit`|float|The realized p&l of the position|
|`crossCurrency`|string|Y => It is cross currency position  <br>N => It is not a cross currency position|
|`rbiRefRate`|float|Incase of cross currency position, the rbi reference rate will be required to calculate the p&l|
|`qtyMulti_com`|float|Incase of commodity positions, this multiplier is required for p&l calculation|
|`segment`|int|The segment in which the position is taken.  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Segments)|
|`exchange`|int|The exchange in which the position is taken.  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Exchanges)|
|`slNo`|int|This is used for sorting of positions|
|`fytoken`|string|Fytoken is a unique identifier for every symbol.  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Fytoken)|
|`cfBuyQty`|int|Carry forward buy quantity|
|`cfSellQty`|int|Carry forward sell quantity|
|`dayBuyQty`|int|Day forward buy quantity|
|`daySellQty`|int|Day forward sell quantity|
|`exchange`|int|The exchange in which order is placed  <br>[View Details](https://myapi.fyers.in/docsv3#tag/Appendix/Exchanges)|
|`buyVal`|float|Total buy value of the position.|
|`sellVal`|float|Total sell value of the position.|

### Request samples

- Python
- Node
- Web modular API
- C#
- Java

Copy

from fyers_apiv3.FyersWebsocket import order_ws

def onPosition(message):
    """
    Callback function to handle incoming messages from the FyersDataSocket WebSocket.

    Parameters:
        message (dict): The received message from the WebSocket.

    """
    print("Position Response:", message)

def onerror(message):
    """
    Callback function to handle WebSocket errors.

    Parameters:
        message (dict): The error message received from the WebSocket.


    """
    print("Error:", message)

def onclose(message):
    """
    Callback function to handle WebSocket connection close events.
    """
    print("Connection closed:", message)

def onopen():
    """
    Callback function to subscribe to data type and symbols upon WebSocket connection.

    """
    # Specify the data type and symbols you want to subscribe to
    data_type = "OnPositions"

    # data_type = "OnOrders"
    # data_type = "OnTrades"
    # data_type = "OnGeneral"
    # data_type = "OnOrders,OnTrades,OnPositions,OnGeneral"

    fyers.subscribe(data_type=data_type)

    # Keep the socket running to receive real-time data
    fyers.keep_running()

# Replace the sample access token with your actual access token obtained from Fyers
access_token = "Xxxxx67IM-100:eyJxxxxxxIUzI1NiJ9.eyJpc3MiOiJhcGkuZnllcnMuaW4iLCJpYXQiOjE2OTA5NTMyNjAsImV4cCI6MTY5MTAyMjYyMCwibmJmIjoxNjkwOTUzMjYwLCJhdWQiOlsieDowIiwieDoxIiwieDoyIiwiZDoxIiwiZDoyIiwieDoxIiwieDowIl0sInN1YiI6ImFjY2Vzc190b2tlbiIsImF0X2hhc2giOiJnQUFBQUFCa3llWXMtX1FSSVdRLUItcUxENUdodFMxZ3JjeTZvREhSbjJhNE5EUEN2TWJLSEc1UEtaM3NqNWE5YWNzNDVueDQ1dHhkeWpqS1lNU1VTTmp2eDhfMlppXzNHQ2pJVkxDcE14U1BLUlhRTkFYV29xYz0iLCJkaXNwbGF5X25hbWUiOiJWSU5BWSBLVU1BUiBNQVVSWUEiLCJvbXMiOiJLMSIsImhzbV9rZXkiOiIwYTU1NjU0ZGE5ZGM4NTMxMTFjN2FjMjQ2MzZlOTI1NDExMTBiN2M1MmNjNWNiZDE0MDA2OTA1NyIsImZ5X2lkIjoiWFYyMDk4NiIsImFwcFR5cGUiOjEwMCwicG9hX2ZsYWciOiJOIn0.vDp4UV_JIPxxxxGXLQOT7NnGxxxxNSBoLo"

# Create a FyersDataSocket instance with the provided parameters
fyers = order_ws.FyersOrderSocket(
    access_token=access_token,  # Your access token for authenticating with the Fyers API.
    write_to_file=False,        # A boolean flag indicating whether to write data to a log file or not.
    log_path="",                # The path to the log file if write_to_file is set to True (empty string means current directory).
    on_connect=onopen,          # Callback function to be executed upon successful WebSocket connection.
    on_close=onclose,           # Callback function to be executed when the WebSocket connection is closed.
    on_error=onerror,           # Callback function to handle any WebSocket errors that may occur.
    on_positions=onPosition,    # Callback function to handle position-related events from the WebSocket.
)

# Establish a connection to the Fyers WebSocket
fyers.connect()

------------------------------------------------------------------------------------------------------------------------------------------
Sample Success Response 
------------------------------------------------------------------------------------------------------------------------------------------
          
  {
    "s":"ok",
    "positions":{
        "symbol":"NSE:IDEA-EQ",
        "id":"NSE:IDEA-EQ-INTRADAY",
        "buyAvg":8,
        "buyQty":1,
        "buyVal":8,
        "sellAvg":7.95,
        "sellQty":1,
        "sellVal":7.95,
        "netAvg":0,
        "netQty":0,
        "side":0,
        "qty":0,
        "productType":"INTRADAY",
        "realized_profit":-0.04999999999999982,
        "rbiRefRate":1,
        "fyToken":"101000000014366",
        "exchange":10,
        "segment":10,
        "dayBuyQty":1,
        "daySellQty":1,
        "cfBuyQty":0,
        "cfSellQty":0,
        "qtyMulti_com":1
    }
  }

## [](https://myapi.fyers.in/docsv3#tag/Web-Socket/paths/~1GeneralSocket/patch)General Socket (general)

The WebSocket API for receiving order, position, trade, price alerts, and EDIS updates is a real-time communication protocol designed to provide seamless access to various critical elements of a trading and EDIS system. This API allows traders and developers to establish a persistent, bidirectional connection with the server, enabling them to receive real-time updates on their orders, current positions, executed trades, price alerts, and EDIS status.

### Request samples

- Python
- Node
- Web modular API
- C#
- Java

Copy

from fyers_apiv3.FyersWebsocket import order_ws

def onTrade(message):
    """
    Callback function to handle incoming messages from the FyersDataSocket WebSocket.

    Parameters:
        message (dict): The received message from the WebSocket.

    """
    print("Trade Response:", message)

def onOrder(message):
    """
    Callback function to handle incoming messages from the FyersDataSocket WebSocket.

    Parameters:
        message (dict): The received message from the WebSocket.

    """
    print("Order Response:", message)

def onPosition(message):
    """
    Callback function to handle incoming messages from the FyersDataSocket WebSocket.

    Parameters:
        message (dict): The received message from the WebSocket.

    """
    print("Position Response:", message)

def onGeneral(message):
    """
    Callback function to handle incoming messages from the FyersDataSocket WebSocket.

    Parameters:
        message (dict): The received message from the WebSocket.

    """
    print("General Response:", message)
def onerror(message):
    """
    Callback function to handle WebSocket errors.

    Parameters:
        message (dict): The error message received from the WebSocket.


    """
    print("Error:", message)

def onclose(message):
    """
    Callback function to handle WebSocket connection close events.
    """
    print("Connection closed:", message)

def onopen():
    """
    Callback function to subscribe to data type and symbols upon WebSocket connection.

    """
    # Specify the data type and symbols you want to subscribe to
    # data_type = "OnOrders"
    # data_type = "OnTrades"
    # data_type = "OnPositions"
    # data_type = "OnGeneral"
    data_type = "OnOrders,OnTrades,OnPositions,OnGeneral"

    fyers.subscribe(data_type=data_type)

    # Keep the socket running to receive real-time data
    fyers.keep_running()

# Replace the sample access token with your actual access token obtained from Fyers
access_token = "Xxxxx67IM-100:YYYYYYYYYYYY"

# Create a FyersDataSocket instance with the provided parameters
fyers = order_ws.FyersOrderSocket(
    access_token=access_token,  # Your access token for authenticating with the Fyers API.
    write_to_file=False,        # A boolean flag indicating whether to write data to a log file or not.
    log_path="",                # The path to the log file if write_to_file is set to True (empty string means current directory).
    on_connect=onopen,          # Callback function to be executed upon successful WebSocket connection.
    on_close=onclose,           # Callback function to be executed when the WebSocket connection is closed.
    on_error=onerror,           # Callback function to handle any WebSocket errors that may occur.
    on_general=onGeneral,       # Callback function to handle general events from the WebSocket.
    on_orders=onOrder,          # Callback function to handle order-related events from the WebSocket.
    on_positions=onPosition,    # Callback function to handle position-related events from the WebSocket.
    on_trades=onTrade           # Callback function to handle trade-related events from the WebSocket.
)

# Establish a connection to the Fyers WebSocket
fyers.connect()

------------------------------------------------------------------------------------------------------------------------------------------
Sample Success Response 
------------------------------------------------------------------------------------------------------------------------------------------
          
  {
    "s":"ok",
    "orders":{
        "clientId":"XV20986",
        "id":"23080400089344",
        "exchOrdId":"1100000009596016",
        "qty":1,
        "filledQty":1,
        "limitPrice":7.95,
        "type":2,
        "fyToken":"101000000014366",
        "exchange":10,
        "segment":10,
        "symbol":"NSE:IDEA-EQ",
        "instrument":0,
        "offlineOrder":false,
        "orderDateTime":"04-Aug-2023 10:12:58",
        "orderValidity":"DAY",
        "productType":"INTRADAY",
        "side":-1,
        "status":90,
        "source":"W",
        "ex_sym":"IDEA",
        "description":"VODAFONE IDEA LIMITED",
        "orderNumStatus":"23080400089344:2"
    }
  }

## [](https://myapi.fyers.in/docsv3#tag/Web-Socket/paths/~1WebSocket/get)Market Data Symbol Update

The WebSocket API for receiving stock data is a real-time communication protocol designed to provide seamless and low-latency access to live stock market data. This API allows developers and traders to establish a persistent, bidirectional connection with the server, enabling them to receive continuous updates on stock prices, trading volumes, and other relevant market information.

To quickly get started with the WebSocket API and start receiving real-time stock data, you can explore our sample scripts and code examples in our GitHub repository:  
[Data WebSocket Sample Scripts](https://github.com/FyersDev/fyers-api-sample-code/tree/sample_v2/My%20API%20Sample%20Script\(GET%20STARTED\)/websocket%20sample%20script)

## Response Attributes(Market Data Update)

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`symbol`|string|The symbol in fyers symbology format whose data is|
|`ltp`|float|Last traded price of security or asset.|
|`prev_close_price`|float|Previous day's close of security or asset.|
|`high_price`|float|Current day's high of security or asset.|
|`low_price`|float|Current day's low of security or asset.|
|`open_price`|float|Current day's open of security or asset.|
|`ch`|float|Change in price of security or asset today.|
|`chp`|float|Change in price in % of security or asset today.|
|`vol_traded_today`|int|Volume traded for security or asset today.|
|`last_traded_time`|int|Last traded time of security or asset.|
|`bid_size`|int|The bid size key represents the quantity or volume of the security or asset that buyers are willing to purchase at a specific bid price level.|
|`ask_size`|int|The ask size key represents the quantity or volume of the security or asset that sellers are willing to sell at a specific ask price level.|
|`ask_price`|float|The ask price key represents the lowest price at which sellers are willing to sell a particular security or asset.|
|`bid_price`|float|The bid price key represents the highest price at which buyers are willing to purchase a particular security or asset.|
|`last_traded_qty`|int|Last traded quantity of security or asset.|
|`tot_buy_qty`|int|Total buy quantity of security or asset.|
|`tot_sell_qty`|int|Total sell quantity of security or asset.|
|`avg_trade_price`|float|Average trade price of security or asset.|
|`type`|string|cn - connection message  <br>sub - subscribe message  <br>if - index data message  <br>dp - market depth data message  <br>sf - Equity and option data message|

### Request samples

- Python
- Node
- Web modular API
- C#
- Java

Copy

from fyers_apiv3.FyersWebsocket import data_ws

def onmessage(message):
    """
    Callback function to handle incoming messages from the FyersDataSocket WebSocket.

    Parameters:
        message (dict): The received message from the WebSocket.

    """
    print("Response:", message)

def onerror(message):
    """
    Callback function to handle WebSocket errors.

    Parameters:
        message (dict): The error message received from the WebSocket.


    """
    print("Error:", message)

def onclose(message):
    """
    Callback function to handle WebSocket connection close events.
    """
    print("Connection closed:", message)

def onopen():
    """
    Callback function to subscribe to data type and symbols upon WebSocket connection.

    """
    # Specify the data type and symbols you want to subscribe to
    data_type = "SymbolUpdate"

    # Subscribe to the specified symbols and data type
    symbols = ['NSE:SBIN-EQ', 'NSE:ADANIENT-EQ']
    fyers.subscribe(symbols=symbols, data_type=data_type)

    # Keep the socket running to receive real-time data
    fyers.keep_running()

# Replace the sample access token with your actual access token obtained from Fyers
access_token = "XC4XXXXXXM-100:eXXXXXXXXXXXXfZNSBoLo"

# Create a FyersDataSocket instance with the provided parameters
fyers = data_ws.FyersDataSocket(
    access_token=access_token,       # Access token in the format "appid:accesstoken"
    log_path="",                     # Path to save logs. Leave empty to auto-create logs in the current directory.
    litemode=False,                  # Lite mode disabled. Set to True if you want a lite response.
    write_to_file=False,              # Save response in a log file instead of printing it.
    reconnect=True,                  # Enable auto-reconnection to WebSocket on disconnection.
    on_connect=onopen,               # Callback function to subscribe to data upon connection.
    on_close=onclose,                # Callback function to handle WebSocket connection close events.
    on_error=onerror,                # Callback function to handle WebSocket errors.
    on_message=onmessage             # Callback function to handle incoming messages from the WebSocket.
)

# Establish a connection to the Fyers WebSocket
fyers.connect()

  ------------------------------------------------------------------------------------------------------------------------------------------
 Sample Success Response 
 ------------------------------------------------------------------------------------------------------------------------------------------
           
  {
    "ltp":606.4,
    "vol_traded_today":3045212,
    "last_traded_time":1690953622,
    "exch_feed_time":1690953622,
    "bid_size":2081,
    "ask_size":903,
    "bid_price":606.4,
    "ask_price":606.45,
    "last_traded_qty":5,
    "tot_buy_qty":749960,
    "tot_sell_qty":1092063,
    "avg_trade_price":608.2,
    "low_price":605.85,
    "high_price":610.5,
    "open_price":609.85,
    "prev_close_price":620.2,
    "type":"sf",
    "symbol":"NSE:SBIN-EQ",
    "ch":-13.8,
    "chp":-2.23
  }

## [](https://myapi.fyers.in/docsv3#tag/Web-Socket/paths/~1WebSocket/head)Market Data Indices Update

The WebSocket API for receiving stock data is a real-time communication protocol designed to provide seamless and low-latency access to live stock market data. This API allows developers and traders to establish a persistent, bidirectional connection with the server, enabling them to receive continuous updates on stock prices, trading volumes, and other relevant market information.

To quickly get started with the WebSocket API and start receiving real-time stock data, you can explore our sample scripts and code examples in our GitHub repository:  
[Data WebSocket Sample Scripts](https://github.com/FyersDev/fyers-api-sample-code/tree/sample_v2/My%20API%20Sample%20Script\(GET%20STARTED\)/websocket%20sample%20script)

## Response Attributes(Index Update)

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`symbol`|string|The symbol in fyers symbology format whose data is|
|`ltp`|float|Last traded price of security or asset.|
|`prev_close_price`|float|Previous day's close of security or asset.|
|`high_price`|float|Current day's high of security or asset.|
|`low_price`|float|Current day's low of security or asset.|
|`open_price`|float|Current day's open of security or asset.|
|`ch`|float|Change in price of security or asset today.|
|`chp`|float|Change in price in % of security or asset today.|
|`type`|string|cn - connection message  <br>sub - subscribe message  <br>if - index data message  <br>dp - market depth data message  <br>sf - Equity and option data message|

### Request samples

- Python
- Node
- Web modular API
- C#
- Java

Copy

from fyers_apiv3.FyersWebsocket import data_ws

def onmessage(message):
    """
    Callback function to handle incoming messages from the FyersDataSocket WebSocket.

    Parameters:
        message (dict): The received message from the WebSocket.

    """
    print("Response:", message)

def onerror(message):
    """
    Callback function to handle WebSocket errors.

    Parameters:
        message (dict): The error message received from the WebSocket.


    """
    print("Error:", message)

def onclose(message):
    """
    Callback function to handle WebSocket connection close events.
    """
    print("Connection closed:", message)

def onopen():
    """
    Callback function to subscribe to data type and symbols upon WebSocket connection.

    """
    # Specify the data type and symbols you want to subscribe to
    data_type = "SymbolUpdate"

    # Subscribe to the specified symbols and data type
    symbols = ["NSE:NIFTY50-INDEX" , "NSE:NIFTYBANK-INDEX"]
    fyers.subscribe(symbols=symbols, data_type=data_type)

    # Keep the socket running to receive real-time data
    fyers.keep_running()

# Replace the sample access token with your actual access token obtained from Fyers
access_token = "XC4XXXXXXM-100:eXXXXXXXXXXXXfZNSBoLo"

# Create a FyersDataSocket instance with the provided parameters
fyers = data_ws.FyersDataSocket(
    access_token=access_token,       # Access token in the format "appid:accesstoken"
    log_path="",                     # Path to save logs. Leave empty to auto-create logs in the current directory.
    litemode=False,                  # Lite mode disabled. Set to True if you want a lite response.
    write_to_file=False,              # Save response in a log file instead of printing it.
    reconnect=True,                  # Enable auto-reconnection to WebSocket on disconnection.
    on_connect=onopen,               # Callback function to subscribe to data upon connection.
    on_close=onclose,                # Callback function to handle WebSocket connection close events.
    on_error=onerror,                # Callback function to handle WebSocket errors.
    on_message=onmessage             # Callback function to handle incoming messages from the WebSocket.
)

# Establish a connection to the Fyers WebSocket
fyers.connect()

  ------------------------------------------------------------------------------------------------------------------------------------------
 Sample Success Response 
 ------------------------------------------------------------------------------------------------------------------------------------------
  {
     "symbol":"NSE:NIFTY50-INDEX",
      "ch":"-27.95",
      "high_price":"26277.35",
      "ltp":"26188.1",
      "exch_feed_time":"1727428424",
      "chp":"-0.11",
      "low_price":"26166.95",
      "open_price":"26248.25",
      "type":"if",
      "prev_close_price":"26216.05"
  }        
 

## [](https://myapi.fyers.in/docsv3#tag/Web-Socket/paths/~1WebSocket/options)Market Data Depth Update

The WebSocket API for receiving stock data is a real-time communication protocol designed to provide seamless and low-latency access to live stock market data. This API allows developers and traders to establish a persistent, bidirectional connection with the server, enabling them to receive continuous updates on stock prices, trading volumes, and other relevant market information.

To quickly get started with the WebSocket API and start receiving real-time stock data, you can explore our sample scripts and code examples in our GitHub repository:  
[Data WebSocket Sample Scripts](https://github.com/FyersDev/fyers-api-sample-code/tree/sample_v2/My%20API%20Sample%20Script\(GET%20STARTED\)/websocket%20sample%20script)

## Response Attributes(Depth Update)

|**Attribute**|**Data Type**|**Description**|
|---|---|---|
|`symbol`|string|The symbol in fyers symbology format whose data is recieved on socket.|
|`bid_price1-bid_price5`|float|The bid price key represents the highest price at which buyers are willing to purchase a particular security or asset.|
|`ask_price1-ask_price5`|float|The ask price key represents the lowest price at which sellers are willing to sell a particular security or asset.|
|`bid_size1-bid_size5`|integer|The bid size key represents the quantity or volume of the security or asset that buyers are willing to purchase at a specific bid price level.|
|`ask_size1-ask_size5`|integer|The ask size key represents the quantity or volume of the security or asset that sellers are willing to sell at a specific ask price level.|
|`bid_order1-bid_order5`|integer|The number of bid order.|
|`ask_order1-ask_order5`|integer|The number of ask order.|
|`type`|string|cn - connection message  <br>sub - subscribe message  <br>if - index data message  <br>dp - market depth data message  <br>sf - Equity and option data message|

### Request samples

- Python
- Node
- Web modular API
- C#
- Java

Copy

from fyers_apiv3.FyersWebsocket import data_ws

def onmessage(message):
    """
    Callback function to handle incoming messages from the FyersDataSocket WebSocket.

    Parameters:
        message (dict): The received message from the WebSocket.

    """
    print("Response:", message)

def onerror(message):
    """
    Callback function to handle WebSocket errors.

    Parameters:
        message (dict): The error message received from the WebSocket.


    """
    print("Error:", message)

def onclose(message):
    """
    Callback function to handle WebSocket connection close events.
    """
    print("Connection closed:", message)

def onopen():
    """
    Callback function to subscribe to data type and symbols upon WebSocket connection.

    """
    # Specify the data type and symbols you want to subscribe to
    data_type = "DepthUpdate"

    # Subscribe to the specified symbols and data type
    symbols = ['NSE:SBIN-EQ', 'NSE:ADANIENT-EQ']
    fyers.subscribe(symbols=symbols, data_type=data_type)

    # Keep the socket running to receive real-time data
    fyers.keep_running()

# Replace the sample access token with your actual access token obtained from Fyers
access_token = "XXDHHIOKS-100:eajoljXXXXXXXXXX"

# Create a FyersDataSocket instance with the provided parameters
fyers = data_ws.FyersDataSocket(
    access_token=access_token,       # Access token in the format "appid:accesstoken"
    log_path="",                     # Path to save logs. Leave empty to auto-create logs in the current directory.
    litemode=False,                  # Lite mode disabled. Set to True if you want a lite response.
    write_to_file=False,              # Save response in a log file instead of printing it.
    reconnect=True,                  # Enable auto-reconnection to WebSocket on disconnection.
    on_connect=onopen,               # Callback function to subscribe to data upon connection.
    on_close=onclose,                # Callback function to handle WebSocket connection close events.
    on_error=onerror,                # Callback function to handle WebSocket errors.
    on_message=onmessage             # Callback function to handle incoming messages from the WebSocket.
)

# Establish a connection to the Fyers WebSocket
fyers.connect()

  ------------------------------------------------------------------------------------------------------------------------------------------
 Sample Success Response 
 ------------------------------------------------------------------------------------------------------------------------------------------
           
 {
  "bid_price1":606.25,
  "bid_price2":606.2,
  "bid_price3":606.15,
  "bid_price4":606.1,
  "bid_price5":606.05,
  "ask_price1":606.3,
  "ask_price2":606.35,
  "ask_price3":606.4,
  "ask_price4":606.45,
  "ask_price5":606.5,
  "bid_size1":20,
  "bid_size2":902,
  "bid_size3":111,
  "bid_size4":110,
  "bid_size5":979,
  "ask_size1":282,
  "ask_size2":568,
  "ask_size3":2910,
  "ask_size4":1676,
  "ask_size5":2981,
  "bid_order1":1,
  "bid_order2":3,
  "bid_order3":2,
  "bid_order4":2,
  "bid_order5":9,
  "ask_order1":4,
  "ask_order2":2,
  "ask_order3":12,
  "ask_order4":9,
  "ask_order5":17,
  "type":"dp",
  "symbol":"NSE:SBIN-EQ"
}

## [](https://myapi.fyers.in/docsv3#tag/Web-Socket/paths/~1WebSocket/patch)Market Data Lite-Mode

The WebSocket API provides a lightweight and efficient "Lite Mode" for receiving only the Last Traded Price (LTP) updates of specific stock symbols. This mode is designed for users who require real-time access to LTP data without the additional overhead of subscribing to other stock data fields. The Lite Mode allows for seamless integration into applications where only the latest stock prices are needed.

### Request samples

- Python
- Node
- Web modular API
- C#
- Java

Copy

from fyers_apiv3.FyersWebsocket import data_ws

def onmessage(message):
    """
    Callback function to handle incoming messages from the FyersDataSocket WebSocket.

    Parameters:
        message (dict): The received message from the WebSocket.

    """
    print("Response:", message)

def onerror(message):
    """
    Callback function to handle WebSocket errors.

    Parameters:
        message (dict): The error message received from the WebSocket.


    """
    print("Error:", message)

def onclose(message):
    """
    Callback function to handle WebSocket connection close events.
    """
    print("Connection closed:", message)

def onopen():
    """
    Callback function to subscribe to data type and symbols upon WebSocket connection.

    """
    # Specify the data type and symbols you want to subscribe to
    data_type = "SymbolUpdate"

    # Subscribe to the specified symbols and data type
    symbols = ['NSE:SBIN-EQ', 'NSE:ADANIENT-EQ']
    fyers.subscribe(symbols=symbols, data_type=data_type)

    # Keep the socket running to receive real-time data
    fyers.keep_running()

# Replace the sample access token with your actual access token obtained from Fyers
access_token = "XC4XXXXXXM-100:eXXXXXXXXXXXXfZNSBoLo"

# Create a FyersDataSocket instance with the provided parameters
fyers = data_ws.FyersDataSocket(
    access_token=access_token,       # Access token in the format "appid:accesstoken"
    log_path="",                     # Path to save logs. Leave empty to auto-create logs in the current directory.
    litemode=True,                  # Lite mode disabled. Set to True if you want a lite response.
    write_to_file=False,              # Save response in a log file instead of printing it.
    reconnect=True,                  # Enable auto-reconnection to WebSocket on disconnection.
    on_connect=onopen,               # Callback function to subscribe to data upon connection.
    on_close=onclose,                # Callback function to handle WebSocket connection close events.
    on_error=onerror,                # Callback function to handle WebSocket errors.
    on_message=onmessage             # Callback function to handle incoming messages from the WebSocket.
)

# Establish a connection to the Fyers WebSocket
fyers.connect()

------------------------------------------------------------------------------------------------------------------------------------------
 Sample Success Response 
------------------------------------------------------------------------------------------------------------------------------------------
           
  {
    symbol: 'NSE:SBIN-EQ',
    ltp: 500.55,
    type: 'sf'
  }

## [](https://myapi.fyers.in/docsv3#tag/Web-Socket/paths/~1WebSocket/put)Market Data Unsubscribe

To stop receiving real-time data updates for a specific stock symbol or a group of symbols, you can utilize the "unsubscribe" action in the WebSocket API. Sending an "unsubscribe" message will remove the specified symbol(s) from your active subscriptions, and you will no longer receive updates for those symbols. You can check the sample code to know how to unsubscribe to already subscribed symbols.

### Request samples

- Python
- Node
- Web modular API
- C#
- Java

Copy

from fyers_apiv3.FyersWebsocket import data_ws

def onmessage(message):
    """
    Callback function to handle incoming messages from the FyersDataSocket WebSocket.

    Parameters:
        message (dict): The received message from the WebSocket.

    """
    print("Response:", message)
    # After processing or when you decide to unsubscribe for specific symbol and data_type
    # you can use the fyers.unsubscribe() method

    # Example of condition: Unsubscribe when a certain condition is met
    if message['symbol']== 'NSE:SBIN-EQ' and message['ltp'] > 610:
        # Unsubscribe from the specified symbols and data type
        data_type = "SymbolUpdate"
        symbols_to_unsubscribe = ['NSE:SBIN-EQ']
        fyers.unsubscribe(symbols=symbols_to_unsubscribe, data_type=data_type)

def onerror(message):
    """
    Callback function to handle WebSocket errors.

    Parameters:
        message (dict): The error message received from the WebSocket.


    """
    print("Error:", message)

def onclose(message):
    """
    Callback function to handle WebSocket connection close events.
    """
    print("Connection closed:", message)

def onopen():
    """
    Callback function to subscribe to data type and symbols upon WebSocket connection.

    """
    # Specify the data type and symbols you want to subscribe to
    data_type = "SymbolUpdate"

    # Subscribe to the specified symbols and data type
    symbols = ['NSE:SBIN-EQ', 'NSE:ADANIENT-EQ']
    fyers.subscribe(symbols=symbols, data_type=data_type)

    # Keep the socket running to receive real-time data
    fyers.keep_running()

# Replace the sample access token with your actual access token obtained from Fyers
access_token = "XXDHHIOKS-100:eajoljXXXXXXXXXX"

# Create a FyersDataSocket instance with the provided parameters
fyers = data_ws.FyersDataSocket(
    access_token=access_token,       # Access token in the format "appid:accesstoken"
    log_path="",                     # Path to save logs. Leave empty to auto-create logs in the current directory.
    litemode=False,                  # Lite mode disabled. Set to True if you want a lite response.
    write_to_file=False,              # Save response in a log file instead of printing it.
    reconnect=True,                  # Enable auto-reconnection to WebSocket on disconnection.
    on_connect=onopen,               # Callback function to subscribe to data upon connection.
    on_close=onclose,                # Callback function to handle WebSocket connection close events.
    on_error=onerror,                # Callback function to handle WebSocket errors.
    on_message=onmessage             # Callback function to handle incoming messages from the WebSocket.
)

# Establish a connection to the Fyers WebSocket
fyers.connect()

------------------------------------------------------------------------------------------------------------------------------------------
 Sample Success Response 
------------------------------------------------------------------------------------------------------------------------------------------
           
  {'type': 'unsub', 'code': 200, 'message': 'Unsubscribed', 's': 'ok'}

## [](https://myapi.fyers.in/docsv3#tag/Web-Socket/paths/~1WebSocket/delete)Advanced Configuration

The WebSocket queue processing interval is an **Optional** setting that allows you to customize how frequently data in the subscription queue is handled. By default, this interval is set to 1 millisecond, but it can be adjusted to better suit your application's specific needs and performance preferences.

1. **Customizable Interval:** You can set the processing interval anywhere between 1ms to 2000ms (2 seconds), giving you flexibility to optimize performance and responsiveness.
2. **Dynamic Adjustment:** The interval setting can be changed at any time during an active WebSocket session.
3. **Performance Optimization:** Shorter intervals (1-10ms) are ideal for high-frequency trading scenarios that benefit from rapid data processing, while slightly longer intervals (100-500ms) work well for general market data streaming.
4. **Resource Management:** You can tune the interval based on how your application handles incoming data, helping to maintain smooth operation across different environments.

### Request samples

- Node

Copy

const FyersSocket = require("fyers-api-v3").fyersDataSocket

var fyersdata= new FyersSocket("xxxxx-1xx:ey....","logpath",true/*flag to enable disable logging*/)
fyersdata.setQueueProcessInterval(200)  // 200ms - more reasonable interval for queue processing
fyersdata.connect()

# [](https://myapi.fyers.in/docsv3#tag/Order-Websocket-Usage-Guide)Order Websocket Usage Guide

## [](https://myapi.fyers.in/docsv3#tag/Order-Websocket-Usage-Guide/paths/~1OrderWebsocketUsageGuide/head)Introduction

The WebSocket API for receiving order, position, trade, price alerts, and EDIS updates is a real-time communication protocol designed to provide seamless access to various critical elements of a trading and EDIS system. This API allows traders and developers to establish a persistent, bidirectional connection with the server, enabling them to receive real-time updates on their orders, current positions, executed trades, price alerts, and EDIS status.  
This guide provides instructions on integrating the order WebSocket into any programming language.

## [](https://myapi.fyers.in/docsv3#tag/Order-Websocket-Usage-Guide/paths/~1OrderWebsocketUsageGuide/post)Order WebSocket Connection

To connect to order websocket, the below two input params are mandate

1. Websocket endpoint : wss://socket.fyers.in/trade/v3
2. Header:
    
    - Format: **< appId:accessToken >**
    - Sample header format : 7ABXUX38S-100:eyJ0eXAi**********qiTnzd2lGwS17s
    
      
    
  

Based on the programming language chosen, respective socket connection libraries can be used.  
For the reference please find the sample code for socket connection written in Python.

Here, we are making a connection with Fyers order websocket with parameters and callback functions on_message, on_error, on_close, on_open, which are required in the Python socket connection library used and would change as per the other programming library used. Sample callback function is shared below.

Note : Handle accordingly in your Programming language

**Connection Response:**

**On Success:** Returns the socket object

**On Failure:**

Possible Error : Status code 403

1. Error: Handshake status 403 Forbidden -+-+- {'date': 'Tue, 19 Dec 2023 04:46:45 GMT', 'content-length': '0', 'connection': 'keep-alive', 'cf-cache-status': 'DYNAMIC', 'set-cookie': '__cf_bm=BOE16LGB7NHpNqW0AJOuFN1rcL3Q9TgnhmtpBfb3.Wk-1702961205-1- AfmECmK9cbVA2XGvkpx+jFuXyRsJET/ZOQYmw3LyZJ68pYLZTgtpbalvNs09ECZZ4GpPiogeYGhhFo+3PCp20nE=; path=/; expires=Tue, 19-Dec-23 05:16:45 GMT; domain=.fyers.in; HttpOnly; Secure', 'server': 'cloudflare', 'cf-ray': '837d00eec8ed17b6-MAA'} -+-+- b''  
    **Reason** : This error will come when your accessToken is wrong  
    **How to solve** : Provide correct accessToken  
    AccessToken format: **< appID:accesstoken >**
  
2. Error: Handshake status 404 Not Found -+-+- {'date': 'Tue, 19 Dec 2023 10:04:35 GMT', 'content-type': 'text/plain; charset=utf-8', 'content-length': '0', 'connection': 'keep-alive', 'cf-cache-status': 'DYNAMIC', 'set-cookie': '__cf_bm=I5oN6zdeKjfGsicqFiXZ57J5SX2IjsFDspaLIEGKPDE-1702980275-1-Ae+ldjrb3WfSuM7yNOzo3ykOIBQ1m+50QqcIqU26A+wqPIHhIEIGSy9kT2OG3OWNI0hwcmh7U+PnJ/aWWhz6fOA=; path=/; expires=Tue, 19-Dec-23 10:34:35 GMT; domain=.fyers.in; HttpOnly; Secure', 'server': 'cloudflare', 'cf-ray': '837ed28169c817ae-MAA'} -+-+- b''  
    **Reason** : Socket Connection URL would be wrong  
    **How to solve** : Provide valid URL.

**Sample callback function:**

For more reference, please find our on_open callback function code for more reference

### Request samples

- Python

Copy

try:
if self.__ws_object is None:
    if self.write_to_file:
        self.background_flag = True
    header = {"authorization": self.__access_token}
    ws = websocket.WebSocketApp(
        self.__url,
        header=header,
        on_message=lambda ws, msg: self.__on_message(msg),
        on_error=lambda ws, msg: self.On_error(msg),
        on_close=lambda ws, close_code, close_reason: self.__on_close(
            ws, close_code, close_reason
        ),
        on_open=lambda ws: self.__on_open(ws),
    )
    self.t = Thread(target=ws.run_forever)
    self.t.daemon = self.background_flag
    self.t.start()

  #Sample callback function:

    def __on_open(self, ws):
    try:
        if self.__ws_object is None:
        self.__ws_object = ws
        self.ping_thread = threading.Thread(target=self.__ping)
        self.ping_thread.start()
    except Exception as e:
        self.order_logger.error(e)
        self.On_error(e)   

## [](https://myapi.fyers.in/docsv3#tag/Order-Websocket-Usage-Guide/paths/~1OrderWebsocketUsageGuide/get)Subscribe Method

Once the connection is established, it is required to subscribe for required actions to get the data. To subscribe for different actions, create a message data, which would be the string format for json node.

```
message = json.dumps( {"T": "SUB_ORD", "SLIST": action_data, "SUB_T": 1} )
```

**Json node Params:**

**T**: Type: String  
value: “SUB_ORD” (Fixed)

**action_data**: Type: List/Array  
Value: ['orders', 'trades', 'positions', 'edis', 'pricealerts', 'login'] Note: Based on the list passed in action_data web_socket data will be received

**SUB_T**: Integer  
Value: 1 (value 1 is for subscribing and -1 for unsubscribe)

Convert the json to string and send this message to socket to subscribe for action_data mentioned

**Sample Response:**

```
{'code': 1605, 'message': 'Successfully subscribed', 's': 'ok'}
```

**Response from socket on any action triggered**

Once the subscribed successfully, for any action triggered, data will be received through socket, if any callback function is defined, would receive on function.

Response would be string, In node we get as array buffer and in python we string, then it parsed to required format. In another programming language you might get in another format you just have to change in string.

**Type:** string  
**Value:** {"orders":{"client_id":"XP0001","exchange":10,"fy_token":"10100000001628","id":"23121800292158","id_fyers":"df013f50-6925-4e2d-ba0f-0becf1229298","instrument":0,"lot_size":1,"offline_flag":false,"oms_flag":"K:1","ord_source":"W","ord_status":20,"ord_type":2,"ordertag":"2:Untagged","org_ord_status":4,"pan":"LVJPS3998E","precision":2,"price_multiplier":1,"product_type":"CNC","qty":1,"qty_multiplier":1,"qty_remaining":1,"report_type":"New Ack","segment":10,"status_msg":"New Ack","symbol":"NSE:BECTORFOOD-EQ","symbol_desc":"MRS BECTORS FOOD SPE LTD","symbol_exch":"BECTORFOOD", "tick_size":0.05,"time_epoch_oms":1702887690,"time_exch":"NA","time_oms":"18-Dec-2023 13:51:30","tran_side":1,"update_time_epoch_oms":1702887690,"update_time_exch":"01-Jan-1970 05:30:00","validity":"DAY"},"s":"ok"}

Note:

1. Above response would be in the string format (In Python ) and arraybuffer (In Node). You have to check in which format you are getting data from websocket as it is dependent on the websocket library for the particular language.
2. Once you get data, you have to change into the string.(if already in string format then no need to change). After that, you have to change this string to JSON. Here you find the following keys as a JSON Key (One of them ) : orders, trades, positions.
3. Now Based on the Key the data is identified, if key is orders it means it is order update message, if key is trades then this message is for trades updates and same for positions updates.
4. In an Fyers SDK the socket raw response is parsed to generate data with required keys and remove the unnecessary keys  
      
    **Parsed Data:** {'s': 'ok', 'orders': {'clientId': 'XP03754', 'id': '23121800388066', 'qty': 1, 'remainingQuantity': 1, 'type': 2, 'fyToken': '10100000002705', 'exchange': 10, 'segment': 10, 'symbol': 'NSE:PRAJIND-EQ', 'instrument': 0, 'offlineOrder': False, 'orderDateTime': '18-Dec-2023 16:33:24', 'orderValidity': 'DAY', 'productType': 'CNC', 'side': 1, 'status': 4, 'source': 'W', 'ex_sym': 'PRAJIND', 'description': 'PRAJ INDUSTRIES LTD', 'orderNumStatus': '23121800388066:4'}}  
      
    All the keys information for orders updates are available there : [Link](https://myapi.fyers.in/docsv3#tag/Web-Socket/paths/~1GeneralSocket/post)  
    All the keys information for Trades updates are available there : [Link](https://myapi.fyers.in/docsv3#tag/Web-Socket/paths/~1GeneralSocket/get)  
    All the keys information for positions updates are available there : [Link](https://myapi.fyers.in/docsv3#tag/Web-Socket/paths/~1GeneralSocket/put)
  
6. Also attaching our internal mapping for your reference, how we are changing the keys from raw data to final data.  
    
            "position_mapper" :
             {
                    "symbol": "symbol",
                    "id": "id",
                    "buy_avg": "buyAvg",
                    "buy_qty": "buyQty",
                    "buy_val": "buyVal",
                    "sell_avg": "sellAvg",
                    "sell_qty": "sellQty",
                    "sell_val": "sellVal",
                    "net_avg": "netAvg",
                    "net_qty": "netQty",
                    "tran_side": "side",
                    "qty": "qty",
                    "product_type": "productType",
                    "pl_realized": "realized_profit",
                    "rbirefrate": "rbiRefRate",
                    "fy_token": "fyToken",
                    "exchange": "exchange",
                    "segment": "segment",
                    "day_buy_qty": "dayBuyQty",
                    "day_sell_qty": "daySellQty",
                    "cf_buy_qty": "cfBuyQty",
                    "cf_sell_qty": "cfSellQty",
                    "qty_multiplier": "qtyMulti_com",
                    "pl_total": "pl",
                    "cross_curr_flag": "crossCurrency",
                    "pl_unrealized": "unrealized_profit"
            },
              "order_mapper" : 
            {
                    "client_id":"clientId",
                    "id":"id",
                    "id_parent":"parentId",
                    "id_exchange":"exchOrdId",
                    "qty":"qty",
                    "qty_remaining":"remainingQuantity",
                    "qty_filled":"filledQty",
                    "price_limit":"limitPrice",
                    "price_stop":"stopPrice",
                    "tradedPrice":"price_traded",
                    "ord_type":"type",
                    "fy_token":"fyToken",
                    "exchange":"exchange",
                    "segment":"segment",
                    "symbol":"symbol",
                    "instrument":"instrument",
                    "oms_msg":"message",
                    "offline_flag":"offlineOrder",
                    "time_oms":"orderDateTime",
                    "validity":"orderValidity",
                    "product_type":"productType",
                    "tran_side":"side",
                    "org_ord_status":"status",
                    "ord_source":"source",
                    "symbol_exch":"ex_sym",
                    "symbol_desc":"description"
              },
                "trade_mapper" : 
              {
                    "id_fill": "tradeNumber",
                    "id": "orderNumber",
                    "qty_traded": "tradedQty",
                    "price_traded": "tradePrice",
                    "traded_val": "tradeValue",
                    "product_type": "productType",
                    "client_id": "clientId",
                    "id_exchange": "exchangeOrderNo",
                    "ord_type": "orderType",
                    "tran_side": "side",
                    "symbol": "symbol",
                    "fill_time": "orderDateTime",
                    "fy_token": "fyToken",
                    "exchange": "exchange",
                    "segment": "segment"
              }
              
    

### Request samples

- Python

Copy

def subscribe(self, data_type: str) -> None:
"""
Subscribes to real-time updates of a specific data type.

Args:
    data_type (str): The type of data to subscribe to, such as orders, position, or holdings.


"""

try:
    if self.__ws_object is not None:
        self.data_type = []
        for elem in data_type.split(","):
            if isinstance(self.socket_type[elem], list):
                self.data_type.extend(self.socket_type[elem])
            else:
                self.data_type.append(self.socket_type[elem])
        
        print("Data type is ", self.data_type)
        print("Data type is ", type(self.data_type))
        message = json.dumps(
            {"T": "SUB_ORD", "SLIST": self.data_type, "SUB_T": 1}
        )
        self.__ws_object.send(message)

except Exception as e:
    self.order_logger.error(e) 

## [](https://myapi.fyers.in/docsv3#tag/Order-Websocket-Usage-Guide/paths/~1OrderWebsocketUsageGuide/put)UnSubscribe Method

To Unsubscribe for different actions, create a message data, which would be the string format for json node.

```
message = json.dumps( {"T": "SUB_ORD", "SLIST": action_data, "SUB_T": -1} )
```

**Json node Params:**

**T**: Type: String  
value: “SUB_ORD” (Fixed)

**action_data**: Type: List/Array  
Value: ['orders', 'trades', 'positions', 'edis', 'pricealerts', 'login'] Note: Based on the list passed in action_data web_socket data will be received

**SUB_T**: Integer  
Value: -1 (value -1 is for unsubscribing and 1 for subscribe)

Convert the json to string and send this message to socket to subscribe for action_data mentioned

### Request samples

- Python

Copy

def unsubscribe(self, data_type: str) -> None:
  """
    Unsubscribes from real-time updates of a specific data type.

  Args:
  data_type (str): The type of data to unsubscribe from, such as orders, position, holdings or general.

  """

  try:
    if self.__ws_object is not None:
      self.data_type = [
        self.socket_type[(type)] for type in data_type.split(",")
      ]
      message = json.dumps(
        {"T": "SUB_ORD", "SLIST": self.data_type, "SUB_T": -1}
      )
      self.__ws_object.send(message)

except Exception as e:
  self.order_logger.error(e)

## [](https://myapi.fyers.in/docsv3#tag/Order-Websocket-Usage-Guide/paths/~1OrderWebsocketUsageGuide/patch)Ping Method

To check whether the websocket connection is alive or not, we have to send a periodically “ping” message. If we get a pong from websocket, it means it is alive else dead. Find how we are doing in Python Code.

Here there is one while loop with sleep of 10 seconds and we send a “ping” message to websocket to know that websocket is alive or not.

### Request samples

- Python

Copy

def __ping(self) -> None:
  """
  Sends periodic ping messages to the server to maintain the WebSocket connection.

  The method continuously sends "__ping" messages to the server at a regular interval
  as long as the WebSocket connection is active.

  """

  while (
      self.__ws_object is not None
      and self.__ws_object.sock
      and self.__ws_object.sock.connected
  ):
      self.__ws_object.send("ping")
      time.sleep(10)

## [](https://myapi.fyers.in/docsv3#tag/Order-Websocket-Usage-Guide/paths/~1OrderWebsocketUsageGuide/options)Mandatory fields

|**Method**|**Fields**|**Reason**|
|---|---|---|
|WebSocket Connection|WebSocket Connection URL(Endpoint)|To make a connection|
|WebSocket Connection|Headers|To authorize|
|Subscribe Method|action_data|To subscribe for particular actions|
|Subscribe Method|"SUB_T": 1|While subscribing to any action|
|UnSubscribe Method|"SUB_T": -1|While unsubscribing any action|

# [](https://myapi.fyers.in/docsv3#tag/Tbtws)Tick-by-Tick (TBT) Websocket Usage Guide

## [](https://myapi.fyers.in/docsv3#tag/Tbtws/paths/~1TBTWebsocketUsageGuide/head)Introduction

Tick-by-tick data is the most detailed market data, recording every trade and order book update in real-time. Each "tick" includes the price, volume, and timestamp of individual trades, as well as changes to buy and sell orders. This granular data is crucial for analyzing market microstructure, tracking order flow, and developing high-frequency trading strategies.  
  

#### Key Points:

  

1. **Available for NFO and NSE Instruments Only**
    - Tick-by-tick data is exclusively available only for **NFO (NSE Futures & Options) and NSE (Equity) instruments.**
2. **Data Formats**
    - **Requests** are sent in **JSON** format.
    - **Responses** are received in **protobuf** format (a compact, efficient data format).
3. **Incremental Data Updates**
    - Instead of sending the full market data repeatedly, the server only sends **changes (differences)** between the last data packet and the current one.
    - To get the complete picture, users must maintain previous data and **apply these changes.**
    - The official SDKs provided by **Fyers** will handle this process automatically.
4. **Snapshot Data on New Subscriptions**
    - When a user **subscribes to tick-by-tick data**, the first packet received is a **snapshot**, containing the full market data at that moment.
    - After this, all subsequent packets only contain **updates (differences)** that need to be applied to the snapshot for a real-time view.

## [](https://myapi.fyers.in/docsv3#tag/Tbtws/paths/~1TBTWebsocketUsageGuide/post)TBT WebSocket Connection [50 Market Depth]

Currently, these are the features available on the socket

|Feature|Description|Status|
|---|---|---|
|TBT 50 Market Depth|TBT 50 Market Depth provides users wtih 50 levels of market depth. [Learn more](https://fyers.in/community/blogs-gdppin8d/post/introducing-50-market-depth-a-game-changer-for-scalpers-and-active-traders-QBRCbSQrTGtQqFB)|Available|
|TBT Quotes|TBT Quotes provides users with quote data such as ltp, ltt, ltq, oi etc|Coming soon|
|TBT DayQuote|TBT DayQuote provides users with day quote data such as day ohlcv oi|Coming soon|
|TBT OHLCV|TBT OHLCV provides users with ohlcv data on the smallest timeframe. This is the most accurate data as spikes are also captured in this data.|Coming soon|

To connect to tbt websocket, the below input params are mandated

1. Websocket endpoint : wss://rtsocket-api.fyers.in/versova
2. Header:  
    Key: Authorization
    - Format: **< appId:accessToken >**
    - Sample header format : 7ABXUX38S-100:eyJ0eXAi**********qiTnzd2lGwS17s

### Request samples

- Python
- Node

Copy

from fyers_apiv3.FyersWebsocket.tbt_ws import FyersTbtSocket, SubscriptionModes

def onopen():
    """
    Callback function to subscribe to data type and symbols upon WebSocket connection.

    """
    print("Connection opened")
    # Specify the data type and symbols you want to subscribe to
    mode = SubscriptionModes.DEPTH
    Channel = '1'
    # Subscribe to the specified symbols and data type
    symbols = ['NSE:NIFTY25MARFUT', 'NSE:BANKNIFTY25MARFUT']
    
    fyers.subscribe(symbol_tickers=symbols, channelNo=Channel, mode=mode)
    fyers.switchChannel(resume_channels=[Channel], pause_channels=[])

    # Keep the socket running to receive real-time data
    fyers.keep_running()

def on_depth_update(ticker, message):
    """
    Callback function to handle incoming messages from the FyersDataSocket WebSocket.

    Parameters:
        ticker (str): The ticker symbol of the received message.
        message (Depth): The received message from the WebSocket.

    """
    print("ticker", ticker)
    print("depth response:", message)
    print("total buy qty:", message.tbq)
    print("total sell qty:", message.tsq)
    print("bids:", message.bidprice)
    print("asks:", message.askprice)
    print("bidqty:", message.bidqty)
    print("askqty:", message.askqty)
    print("bids ord numbers:", message.bidordn)
    print("asks ord numbers:", message.askordn)
    print("issnapshot:", message.snapshot)
    print("tick timestamp:", message.timestamp)

def onerror(message):
    """
    Callback function to handle WebSocket errors.

    Parameters:
        message (dict): The error message received from the WebSocket.

    """
    print("Error:", message)

def onclose(message):
    """
    Callback function to handle WebSocket connection close events.
    """
    print("Connection closed:", message)

def onerror_message(message):
    """
    Callback function for error message events from the server

    Parameters:
        message (dict): The error message received from the Server.

    """
    print("Error Message:", message)

# Replace the sample access token with your actual access token obtained from Fyers
access_token = "XCXXXXXXM-100:eyJ0tHfZNSBoLo"

fyers = FyersTbtSocket(
    access_token=access_token,  # Your access token for authenticating with the Fyers API.
    write_to_file=False,        # A boolean flag indicating whether to write data to a log file or not.
    log_path="",                # The path to the log file if write_to_file is set to True (empty string means current directory).
    on_open=onopen,          # Callback function to be executed upon successful WebSocket connection.
    on_close=onclose,           # Callback function to be executed when the WebSocket connection is closed.
    on_error=onerror,           # Callback function to handle any WebSocket errors that may occur.
    on_depth_update=on_depth_update, # Callback function to handle depth-related events from the WebSocket
    on_error_message=onerror_message         # Callback function to handle server-related erros from the WebSocket.
)
# Establish a connection to the Fyers WebSocket
fyers.connect()

## [](https://myapi.fyers.in/docsv3#tag/Tbtws/paths/~1TBTWebsocketUsageGuide/put)Concept of channels

With the Tick-by-Tick (TBT) WebSocket, we are introducing the concept of channels. A channel acts as a logical grouping for different subscribed symbols, making it easier to manage data streams efficiently.

### How Channels Work

- When subscribing to market data, you need to specify both the symbols and a channel number.
- Simply subscribing to a channel does not start the data stream—you must also resume the channel to begin receiving updates.

### Example Usage

Let’s say you organize your subscriptions as follows:

- Channel 1: All Nifty-related symbols
- Channel 2: All BankNifty-related symbols

Now, depending on what data you need, you can control the channels dynamically:

- To receive only Nifty data → Pause Channel 2 and Resume Channel 1
- To receive only BankNifty data → Pause Channel 1 and Resume Channel 2
- To receive both Nifty and BankNifty data → Resume both channels

This approach provides greater flexibility and control over market data streaming, allowing you to filter and manage real-time data efficiently.

## [](https://myapi.fyers.in/docsv3#tag/Tbtws/paths/~1TBTWebsocketUsageGuide/get)Request Message Types

|Type|Purpose|Encoding Format|Data Format|
|---|---|---|---|
|Ping|Ping message to keep connection alive|String|"ping"|
|Subscribe|Subscribe to the symbols for which data is required|Json string|{<br>        "type": 1,<br>        "data": {<br>            "subs": 1,<br>            "symbols": ["NSE:IOC25FEBFUT", "NSE:NIFTY25FEBFUT", <br>            "NSE:BANKNIFTY25FEBFUT", "NSE:FINNIFTY25FEBFUT", "NSE:TCS25FEBFUT"],<br>            "mode": "depth",<br>            "channel": "1"<br>        }<br>      }|
|Unsubscribe|Unsubscribe to the symbols for which data is NOT required|Json string|{<br>        "type": 1,<br>        "data": {<br>            "subs": -1,<br>            "symbols": ["NSE:IOC25FEBFUT", "NSE:NIFTY25FEBFUT", <br>            "NSE:BANKNIFTY25FEBFUT", "NSE:FINNIFTY25FEBFUT", "NSE:TCS25FEBFUT"],<br>            "mode": "depth",<br>            "channel": "1"<br>        }<br>      }|
|Switch Channel|Switch between active and paused channels|Json string|{<br>          "type": 2,<br>          "data": {<br>              "resumeChannels": ["1"],<br>              "pauseChannels": []<br>          }<br>      }|

## [](https://myapi.fyers.in/docsv3#tag/Tbtws/paths/~1TBTWebsocketUsageGuide/patch)Response Message Types

We use Protocol Buffers (protobuf) as the response format for all market data. The .proto file, which defines the data structure, is available at:

📌 Proto URL: [https://public.fyers.in/tbtproto/1.0.0/msg.proto](https://public.fyers.in/tbtproto/1.0.0/msg.proto)

Protobuf is a widely used data format, and compilers are available to generate code in different programming languages.

How to Install and Use Protobuf  

- Protobuf Compiler Installation: [https://protobuf.dev/getting-started/](https://protobuf.dev/getting-started/)
- Using Protobuf with Python: [https://protobuf.dev/reference/python/python-generated/](https://protobuf.dev/reference/python/python-generated/)
- Using Protobuf with Node.js: [https://www.npmjs.com/package/protobufjs](https://www.npmjs.com/package/protobufjs)

We have uploaded the compiled files also for python, nodejs, and golang. You can download the files from the below link: [https://public.fyers.in/tbtproto/1.0.0/protogencode.zip](https://public.fyers.in/tbtproto/1.0.0/protogencode.zip)  
Copy the required file directly in your project and use it.

#### Proto Versions and Links:

|Proto Version|Proto URL|Compiled files URL|Updated on|
|---|---|---|---|
|1.0.0|[https://public.fyers.in/tbtproto/1.0.0/msg.proto](https://public.fyers.in/tbtproto/1.0.0/msg.proto)|[https://public.fyers.in/tbtproto/1.0.0/protogencode.zip](https://public.fyers.in/tbtproto/1.0.0/protogencode.zip)|20-02-2025|

|Type|Data Format|Field Explanation|
|---|---|---|
|SocketMessage|- type: value will always be MessageType.depth<br>- feeds: string (key) will be the symbol ticker and value will be the [MarketFeed](https://myapi.fyers.in/docsv3#mfeed) datastructure. This value will have the actual 50 depth values<br>- snapshot: true if its a snapshot and false if its a diff packet<br>- msg: will mostly contain error msgs when error = true<br>- error: true if it is an error, else false. In case of true, feeds will be nil/empty|message SocketMessage {<br>      MessageType type = 1;<br>      map<string, MarketFeed> feeds = 2;<br>      bool snapshot = 3;<br>      string msg = 4;<br>      bool error = 5;<br>}|
|MarketFeed|- depth: [Depth](https://myapi.fyers.in/docsv3#depth) datastructure. This field will have the actual market depth value<br>- feed_time: time of the packet in unix epoch<br>- send_time: time of the packet at the time of sending from server<br>- token: fytoken for the symbol<br>- snapshot: true if its a snapshot else false for a diff packet<br>- ticker: symbol ticker<br>**Note:** other fields can be ignored|message MarketFeed {<br>    Quote quote = 1;<br>    ExtendedQuote eq = 2;<br>    DailyQuote dq = 3;<br>    OHLCV ohlcv = 4;<br>    Depth depth = 5;<br>    google.protobuf.UInt64Value feed_time = 6; <br>    google.protobuf.UInt64Value send_time = 7;<br>    string token = 8;<br>    uint64 sequence_no = 9;<br>    bool snapshot = 10;<br>    string ticker = 11;<br>    SymDetail symdetail = 12;<br>}|
|Depth|- tbq: total bid qty<br>- tsq: total sell qty<br>- asks: array of asks of type [Marketlevel](https://myapi.fyers.in/docsv3#mlevel) datastructure<br>- bids: array of bids of type [Marketlevel](https://myapi.fyers.in/docsv3#mlevel) datastructure|message Depth {<br>    google.protobuf.UInt64Value tbq = 1;                <br>    google.protobuf.UInt64Value tsq = 2;        <br>    repeated MarketLevel asks = 3;                 <br>    repeated MarketLevel bids = 4;                       <br>}|
|MarketLevel|- price: price<br>- qty: qty in the market depth for the price<br>- nord: number of orders in the market depth for the price<br>- num: depth number, for 50 depth will be between 0 and 49 [0 based array indexing]|message MarketLevel {<br>    google.protobuf.Int64Value price = 1;<br>    google.protobuf.UInt32Value qty  = 2; <br>    google.protobuf.UInt32Value nord = 3; <br>    google.protobuf.UInt32Value num = 4;<br>}|

## [](https://myapi.fyers.in/docsv3#tag/Tbtws/paths/~1TBTWebsocketUsageGuide/delete)Ratelimits

Following ratelimits apply for TBT Websocket:

|Description|Limit|
|---|---|
|Active Connections Per App Per User|3|
|Symbols per connection [Market Depth]|5|
|Channels per connection|50 (1-50)|

# [](https://myapi.fyers.in/docsv3#tag/True-Data-V2)True Data V2

## [](https://myapi.fyers.in/docsv3#tag/True-Data-V2/Introduction)Introduction

Fyers is offering market data APIs in collaboration with Truedata. The data APIs provide both real-time data as well as historical data.

## [](https://myapi.fyers.in/docsv3#tag/True-Data-V2/Truedata-API-Documentation)Truedata API Documentation

You can download the entire Truedata API document [here.](https://www.dropbox.com/sh/xyph0b41dby8lu8/AACAwWUSatV9PjJR7mnqmW78a?dl=0) This document will provide all the different functions which are available, sample requests and responses along with the Python sample code. You can also visit the official Python package on PyPi [here](https://pypi.org/project/truedata-ws/)

## [](https://myapi.fyers.in/docsv3#tag/True-Data-V2/Prerequisites)Prerequisites

Prerequisites to use Python Truedata Websocket library

1. Python 3.7 or above
2. pip install truedata_ws

## [](https://myapi.fyers.in/docsv3#tag/True-Data-V2/How-to-subscribe-to-Truedata-from-FYERS)How to subscribe to Truedata from FYERS ?

You can subscribe to the different Truedata subscription plans from [here](https://subscriptions.fyers.in/true-data.html) You can view your subscription status from [here](https://subscriptions.fyers.in/status/)

# [](https://myapi.fyers.in/docsv3#tag/Appendix)Appendix

## [](https://myapi.fyers.in/docsv3#tag/Appendix/Fytoken)Fytoken

|**Indicator**|**Format**|**Description**|
|---|---|---|
|Exchange|2 Digits|Exchange of the symbol|
|Segment|2 Digits|Segment of the symbol|
|Expiry|6 Digits|Format: YYMMDD  <br>Eg: 200827|
|Exchange Token`|From 2 upto 6 Digits|The token assigned for the symbol by the exchange  <br>Eg:22|

## [](https://myapi.fyers.in/docsv3#tag/Appendix/Exchanges)Exchanges

|Possible Values|Description|
|---|---|
|10|NSE (National Stock Exchange)|
|11|MCX (Multi Commodity Exchange)|
|12|BSE (Bombay Stock Exchange)|

## [](https://myapi.fyers.in/docsv3#tag/Appendix/Segments)Segments

|Possible Values|Description|
|---|---|
|10|Capital Market|
|11|Equity Derivatives|
|12|Currency Derivatives|
|20|Commodity Derivatives|

## [](https://myapi.fyers.in/docsv3#tag/Appendix/Available-Exchange-Segment-Combinations)Available Exchange-Segment Combinations

|Exchange|Segment|Exchange Code|Segment Code|
|---|---|---|---|
|NSE|Capital Market|10|10|
|NSE|Equity Derivatives|10|11|
|NSE|Currency Derivatives|10|12|
|NSE|Commodity Derivatives|10|20|
|BSE|Capital Market|12|10|
|BSE|Equity Derivatives|12|11|
|BSE|Currency Derivatives|12|12|
|MCX|Commodity Derivatives|11|20|

## [](https://myapi.fyers.in/docsv3#tag/Appendix/Instrument-Types)Instrument Types

|Possible Values|Description|
|---|---|
|.|**CM segment**|
|0|EQ (EQUITY)|
|1|PREFSHARES|
|2|DEBENTURES|
|3|WARRANTS|
|4|MISC (NSE, BSE)|
|5|SGB|
|6|G - Secs|
|7|T - Bills|
|8|MF|
|9|ETF|
|10|INDEX|
|50|MISC (BSE)|
|.|**FO segment**|
|11|FUTIDX|
|12|FUTIVX|
|13|FUTSTK|
|14|OPTIDX|
|15|OPTSTK|
|.|**CD segment**|
|16|FUTCUR|
|17|FUTIRT|
|18|FUTIRC|
|19|OPTCUR|
|20|UNDCUR|
|21|UNDIRC|
|22|UNDIRT|
|23|UNDIRD|
|24|INDEX_CD|
|25|FUTIRD|
|.|**COM segment**|
|11|FUTIDX|
|30|FUTCOM|
|31|OPTFUT|
|32|OPTCOM|
|33|FUTBAS|
|34|FUTBLN|
|35|FUTENR|
|36|OPTBLN|
|37|OPTFUT (NCOM)|

## [](https://myapi.fyers.in/docsv3#tag/Appendix/Symbology-Format)Symbology Format

|**Segment**|**Format**|**Examples**|
|---|---|---|
|Equity|{Ex}:{Ex_Symbol}-{Series}|NSE:SBIN-EQ, NSE:ACC-EQ,  <br>NSE:MODIRUBBER-BE  <br>BSE:SBIN-A, BSE:ACC-A,  <br>BSE:MODIRUBBER-T|
|Equity Futures|{Ex}:{Ex_UnderlyingSymbol}{YY}{MMM}FUT|NSE:NIFTY20OCTFUT,  <br>NSE:BANKNIFTY20NOVFUT,  <br>BSE:SENSEX23AUGFUT|
|Equity Options (Monthly Expiry)|{Ex}:{Ex_UnderlyingSymbol}{YY}{MMM}{Strike}{Opt_Type}|NSE:NIFTY20OCT11000CE,  <br>NSE:BANKNIFTY20NOV25000PE ,  <br>BSE:SENSEX23AUG60400CE|
|Equity Options (Weekly Expiry)|{Ex}:{Ex_UnderlyingSymbol}{YY}{M}{dd}{Strike}{Opt_Type}  <br>[refer here for possible values of {M}](https://myapi.fyers.in/docsv3#tag/Appendix/Symbology-Possible-Values)|NSE:NIFTY2010811000CE,  <br>NSE:NIFTY20O0811000CE,  <br>BSE:SENSEX2381161000CE,  <br>NSE:NIFTY20D1025000CE|
|Currency Futures|{Ex}:{Ex_CurrencyPair}{YY}{MMM}FUT|NSE:USDINR20OCTFUT,  <br>NSE:GBPINR20NOVFUT|
|Currency Options (Monthly Expiry)|Ex}:{Ex_CurrencyPair}{YY}{MMM}{Strike}{Opt_Type}|NSE:USDINR20OCT75CE,  <br>NSE:GBPINR20NOV80.5PE|
|Currency Options (Weekly Expiry)|{Ex}:{Ex_CurrencyPair}{YY}{M}{dd}{Strike}{Opt_Type}|NSE:USDINR20O0875CE,  <br>NSE:GBPINR20N0580.5PE  <br>NSE:USDINR20D1075CE|
|Commodity Futures|{Ex}:{Ex_Commodity}{YY}{MMM}FUT|MCX:CRUDEOIL20OCTFUT,  <br>MCX:GOLD20DECFUT|
|Commodity Options (Monthly Expiry)|{Ex}:{Ex_Commodity}{YY}{MMM}{Strike}{Opt_Type}|MCX:CRUDEOIL20OCT4000CE,  <br>MCX:GOLD20DEC40000PE|

## [](https://myapi.fyers.in/docsv3#tag/Appendix/Symbology-Possible-Values)Symbology Possible Values

|**Variable**|**Explanation**|**Possible Values**|
|---|---|---|
|{Ex}|This is the exchange on which the symbol is trading|NSE, BSE, MCX|
|{YY}|This is the last 2 digits of the year|2019 will be 19  <br>2020 will be 2020  <br>2021 will be 21  <br>2022 will be 22|
|{MMM}|For monthly expiries such as futures and options,  <br>this value is the 3 characters of the month. The month  <br>will always be denoted in uppercase.|JAN  <br>FEB  <br>MAR  <br>APR  <br>MAY  <br>JUN  <br>JUL  <br>AUG  <br>SEP  <br>OCT  <br>NOV  <br>DEC|
|{M}|For weekly expiries, this value represents the month  <br>of expiry but with only 1 character. This is a mix  <br>of numbers as well as characters.|Jan => 1  <br>Feb => 2  <br>Mar => 3  <br>Apr => 4  <br>May => 5  <br>Jun => 6  <br>Jul => 7  <br>Aug => 8  <br>Sep => 9  <br>Oct => O (Letter)  <br>Nov => N  <br>Dec => D|
|{dd}|This is used in weekly expiries. This represents  <br>the date of the month on which the contract is  <br>going to expire. This value will always be 2 characters.|01  <br>06  <br>10  <br>25  <br>30|
|{Opt_Type}|This represents whether the contract is call or put|Call Option => CE,  <br>Put Option => PE|
|{Strike}|This is the strike price of the option contract|11000  <br>75.5|

## [](https://myapi.fyers.in/docsv3#tag/Appendix/Product-Types.)Product Types.

|Possible Values|Description|
|---|---|
|CNC|For equity only|
|INTRADAY|Applicable for all segments|
|MARGIN|Applicable only for derivatives|
|CO|Cover Order|
|BO|Bracket Order|
|MTF|Margin Trading Facility|

## [](https://myapi.fyers.in/docsv3#tag/Appendix/Order-Types.)Order Types.

|Possible Values|Description|
|---|---|
|1|Limit order|
|2|Market order|
|3|Stop order (SL-M)|
|4|Stoplimit order (SL-L)|

## [](https://myapi.fyers.in/docsv3#tag/Appendix/Order-Status)Order Status

|Possible Values|Description|
|---|---|
|1|Cancelled|
|2|Traded / Filled|
|3|For future use|
|4|Transit|
|5|Rejected|
|6|Pending|

## [](https://myapi.fyers.in/docsv3#tag/Appendix/Order-Sides)Order Sides

|Possible Values|Description|
|---|---|
|1|Buy|
|-1|Sell|

## [](https://myapi.fyers.in/docsv3#tag/Appendix/Position-Sides)Position Sides

|Possible Values|Description|
|---|---|
|1|Long|
|-1|Short|
|0|Closed position|

## [](https://myapi.fyers.in/docsv3#tag/Appendix/Holding-Types)Holding Types

|Possible Values|Description|
|---|---|
|T1|The shares are purchased but not yet delivered to the demat account.|
|HLD|The shares are purchased and are available in the demat account.|

## [](https://myapi.fyers.in/docsv3#tag/Appendix/Order-Sources)Order Sources

|Possible Values|Description|
|---|---|
|M|Mobile|
|W|Web|
|R|Fyers One|
|A|Admin|
|ITS|API|

# [](https://myapi.fyers.in/docsv3#tag/Change-Log)Change Log

|Date|Changes|
|---|---|
|`22 Aug 2025`|- Fixed missing symbol key in market data indices update.<br>- Updated WebSocket reconnection logic.<br>- Fixed rate limiting issue caused by internet connectivity checks.<br>**Version**:  <br>`Java : fyers-api-v3 - v1.3.0`|
|`23 Jun 2025`|- Added support for NSE equity segment on TBT (Tick by tick) Socket. [Click here for reference](https://myapi.fyers.in/docsv3#tag/Tbtws)|
|`09 Jun 2025`|- Added optional support for customizing WebSocket queue processing interval<br>**Version**:  <br>`Node Js : fyers-web-sdk-v3 - v1.4.2`|
|`16 Apr 2025`|- Added support for logout API in Web Js SDK and Java SDK<br>**Version**:  <br>`Web Js : fyers-web-sdk-v3 - v1.3.1`  <br>`Java : fyers-apiv3 - v1.2.0`|
|`26 Mar 2025`|- Added support for TBT 50 depth in Node SDK<br>- Added support for logout API in node SDK<br>**Version**:  <br>`Node : fyers-api-v3 - v1.4.1`|
|`20 Mar 2025`|- Updated Instrument Types|
|`04 Mar 2025`|**Version**:  <br>`Python : fyers-apiv3 - v3.1.7`  <br><br>- Added support for TBT 50 depth in python SDK<br>- Added [sample code](https://myapi.fyers.in/docsv3#tag/Tbtws/paths/~1TBTWebsocketUsageGuide/post) for TBT 50 depth<br>- Added support for logout API in python SDK|
|`20 Feb 2025`|- [TBT 50 depth](https://myapi.fyers.in/docsv3#tag/Tbtws) websocket documentation|
|`13 Feb 2025`|- Added keys for DDPI and MTF Activation Status in Profile API|
|`05 Feb 2025`|- Introduced Logout API [click here](https://myapi.fyers.in/docsV3#tag/User/paths/~1User/patch)<br>  <br>**Version**:  <br>`Node : fyers-api-v3 - v1.4.0`  <br>`Web Js : fyers-web-sdk-v3 - v1.3.0`  <br>`CDN :fyers-web-sdk-v3 - v1.3.0`  <br>`Java : fyers-apiv3 - v1.1.0`  <br>  <br>- Added MTF and GTT Order Placement|
|`01 Feb 2025`|**Version**:  <br>`C# : fyers-apiv3 - v1.0.6`<br><br>- Added MTF and GTT Order Placement|
|`30 Jan 2025`|**Version**:  <br>`Python : fyers-apiv3 - v3.1.5`<br><br>- Added MTF and GTT Order Placement|
|`20 Jan 2025`|- Introduced MTF and GTT Order Placement APIs|
|`13 Jan 2025`|**Version**:  <br>`C# : fyers-api-v3 - v1.0.5`  <br>`Java : fyers-apiv3 - v1.0.2`  <br><br>- Added key for DisclosedQty in modify order|
|`27 Dec 2024`|**Version**:  <br>`Node : fyers-api-v3 - v1.3.3`  <br>`Web Js : fyers-web-sdk-v3 - v1.2.4`  <br>`CDN :fyers-web-sdk-v3 - v1.2.1`  <br>  <br><br>- Improved compatibility with symbols containing special characters|
|`26 Dec 2024`|**Version**:  <br>`C# : fyers-api-v3 - v1.0.4`  <br>`Java : fyers-apiv3 - v1.0.1`  <br><br>- Fixed Data Socket Issue for Sensex Symbol|
|`10 Oct 2024`|**Version**:  <br>`Python : fyers-apiv3 - v3.1.4`<br><br>- Minor bug fixes within websocket package|
|`09 Oct 2024`|**Version**:  <br>`C# : fyers-api-v3 - v1.0.3`  <br><br>- Added Multileg order feature|
|`03 Oct 2024`|**Version**:  <br>`Java : fyers-api-v3 - v1.0.0`  <br><br>- Introduced API V3 Java SDK|
|`17 Sep 2024`|**Version**:  <br>`C# : fyers-api-v3 - v1.0.2`  <br><br>- Added Option Chain API|
|`22 Aug 2024`|**Version**: `All`  <br>  <br><br>- Increased API rate limit from 10,000 requests per day to 1 Lakh requests per day (10x increase from the previous daily rate limit), [click here](https://myapi.fyers.in/docsV3#tag/Request-and-Response-Structure/paths/~1pet~1%7BpetId%7D/post) to view the current rate limits.  <br>    **Note:** There are no change in per-second and per-minute rate limits<br>  <br>- Updated API document with API Error Codes [refer here](https://myapi.fyers.in/docsV3#tag/Request-and-Response-Structure/paths/~1pet~1%7BpetId%7D/patch)|
|`03 Jul 2024`|**Version**:  <br>`Python : fyers-apiv3 - v3.1.2`  <br>`Node : fyers-api-v3 - v1.3.0`  <br><br>- Added Multileg order feature|
|`12 Jun 2024`|**Version**:  <br>`C# : fyers-api-v3 - v1.0.1`  <br><br>- Optimized package with bug fixes|
|`07 Jun 2024`|**Version**:  <br>`Web Js : fyers-web-sdk-v3 - v1.2.2`  <br><br>- Optimized package|
|`30 May 2024`|**Version**:  <br>`All  <br><br>- Added description for fyers 201 code(order placement)|
|`29 May 2024`|**Version**:  <br>`Python : fyers-apiv3 - v3.1.0`  <br><br>- Improvised logging|
|`14 May 2024`|**Version**:  <br>`Web Js : fyers-web-sdk-v3 - v1.2.1`  <br><br>- Improvised in internal package import logic|
|`25 Apr 2024`|**Version**:  <br>`C# : fyers-api-v3 - v1.0.0`  <br><br>- Introduced API V3 C# SDK|
|`23 Apr 2024`|**Version**:  <br>`Python : fyers-apiv3 - v3.1.0`  <br>`Node : fyers-api-v3 - v1.2.0`  <br>`Web Js : fyers-web-sdk-v3 - v1.2.0`  <br>`CDN :fyers-web-sdk-v3 - v1.2.0`  <br>  <br><br>- Added option chain API|
|`22 Mar 2024`|**Version**: `All`  <br>  <br><br>- Added 2 new reserved columns in Symbol Master CSV files, will be used for future development, kindly ignore|
|`04 Apr 2024`|**Version**: `All`  <br>  <br><br>- Deprecated **cmd** attribute in Quotes API response [click here](https://fyers.in/notice-board/action-required-cmd-field-in-api-to-be-deprecated.html) for more details|
|`26 Mar 2024`|**Version**:  <br>`Python : fyers-apiv3 - v3.1.0`  <br>`Node : fyers-api-v3 - v1.1.1`  <br>`Web Js : fyers-web-sdk-v3 - v1.1.0`  <br>`CDN :fyers-web-sdk-v3 - v1.1.0`  <br>  <br><br>- **Symbol Subscription Enhancement**<br>    - Optimised symbol subscription<br>    - Increased symbol subscription limit from **200** to **5000** in a single connection|
|`22 Mar 2024`|**Version**: `All`  <br>  <br><br>- Added 2 new reserved columns in Symbol Master CSV files, will be used for future development, kindly ignore|
|`15 Mar 2024`|**Version**: `fyers-web-sdk-v3 - v1.0.0`  <br>  <br><br>- Introduced Browser Compatible SDK.|
|`14 Mar 2024`|**Version**: `Python SDK - v3.0.9`  <br>  <br><br>- **Logging Enhancement**<br>    - In the FyersModel class, the log_level parameter has been introduced to control the verbosity of logging. By default, the logging level is set to 'ERROR',only errors will be logged. However, users have the flexibility to set the log_level parameter to 'DEBUG', allowing for more detailed logging. Logs are written **fyersApi.log** file.<br>    - Added **fyersRequest.log** file where requested endpoints and status code are logged (can be used to analyse the API requests made).<br>- **Compatible with Python v3.12**<br>    - Updated aiohttp to version 3.9.3 (latest release) to ensure compatibility with Python 3.12.|
|`13 Mar 2024`|**Version**: `All`  <br>  <br><br>- Added support for seconds candles|
|`05 Dec 2023`|Version: `All`  <br><br>- **Order Placement**<br>    - OrderTagging functionality added.<br>- **Orderbook**<br>    - Orderbook returns Ordertag in response<br>    - Query orderbook by Ordertag<br>- **Tradebook**<br>    - Orderbook returns Ordertag in response<br>    - Query tradebook by Ordertag|
|`18 Aug 2023`|**Version**: `API Version 3`  <br>  <br>**New Features and Updates**  <br><br>- **Performance**  <br>    - Fast Order Placement: Achieving placement within < 75 ms<br>    - Fast get APIs: Achieving response times within < 75 ms<br><br>- **New Data Socket:**<br>    - Improved tick update speed, ensuring swift and efficient market data updates.<br>    - Introducing Lite mode for targeted last traded price (LTP) change updates.<br>    - SymbolUpdate: Real-time symbol-specific updates for instant parameter changes.<br>    - DepthUpdate: Real-time market depth changes for selected symbols.<br>    - Increased subscription capacity, accommodating tracking of 200 symbols.<br>    - Strengthened error handling callbacks for seamless issue resolution.<br><br>- **New Order Socket**<br>    - Real-time updates for orders<br>    - Real-time updates for positions<br>    - Real-time updates for trades<br>    - Real-time updates for eDIS<br>    - Real-time updates for price alerts<br>    - Improved error handling callbacks<br><br>- **URL update for various APIs**<br>    - Enhanced History API available at: [https://api-t1.fyers.in/data/history](https://api-t1.fyers.in/data/history)<br>    - New Market Status API introduced at: [https://api-t1.fyers.in/data/marketStatus](https://api-t1.fyers.in/data/marketStatus)<br>    - Enhanced Quotes API available at: [https://api-t1.fyers.in/data/quotes](https://api-t1.fyers.in/data/quotes)<br>    - Enhanced Market Depth API available at: [https://api-t1.fyers.in/data/depth](https://api-t1.fyers.in/data/depth)<br><br>- **Documentation and Sample Code Updates**<br>    - Added sample code for NodeJS and Python in the documentation<br>    - Updated sample code in the GitHub repository for both Python and NodeJS|
|`04 May 2023`|**Version**: `All`  <br>  <br><br>- **Quotes**<br>    - URL updated to **https://api-t1.fyers.in/data/quotes?symbols=NSE:SBIN-EQ**<br>    - ip updated to lp<br>    - Removed fyToken & prev_close_price from response<br>    - Text updation: "Symbols" changed to "symbol"<br>- **Market Depth**<br>    - URL updated to **https://api-t1.fyers.in/data/depth?symbol=NSE:SBIN-EQ&ohlcv_flag=1**<br>    - itt updated to ltt<br>    - Removed tick_Size & oi from response|
|-|**Version**: `API Version 2`  <br>  <br><br>- **App Related**<br>    - Introduced common apps for third party app developers<br>    - Different authentication methods such as OAuth2, PKCE and OIDC<br>    - Permission templates at the time of app creation<br>- **Authentication**<br>    - Authentication flow has been changed to improve security<br>    - Authorization header value has been changed<br>- **Order placement**<br>    - Multi order placement<br>    - Multi order modification<br>    - Multi order cancellation<br>- **Other**<br>    <br>    - Market status API<br>    <br>    **Realtime Data Rest API**<br>    <br>    - Quotes api to get realtime data for list of symbols via Rest API<br>    - Market Depth API to get bid ask data for a particular symbol<br>    <br>    **Websocket**<br>    <br>    - Get realtime price info for a list of symbols<br>    - Get realtime market depth for a particular symbol<br>    - Get realtime order updates<br>    - Background and Foreground process enabled for websocket.<br>    - User can subscribe to only Index symbols<br>    - Added sample scripts to get started with websocket<br>    - Object initialization method changed a bit (instead of fyers_api.websocket it is fyers_api.Websocket)<br>    - No More Pong received message on the console. The data will be continuous<br>    <br>    **Postback (Webhooks)**<br>    <br>    - Get realtime order updates via postbacks / webhooks<br>    <br>    **Transactions**<br>    - eDIS flow|

© Fyers Securities Pvt. Ltd. All Rights Reserved.[Terms & Conditions](https://fyers.in/terms-and-conditions.php)[Privacy Policy](https://fyers.in/privacy-policy.php)[Support ![open support portal](https://assets.fyers.in/images/website/icon-open-blank.svg)](https://support.fyers.in/)