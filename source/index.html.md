---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript
  - csharp
  - java

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

# search: true

# code_clipboard: true

meta:
  - name: description
    content: Documentation for the RexRetail API
---

# Introduction

Welcome to the RexRetail API! You can use our API to access RexRetail API endpoints, which can get information on various services, solutions, and products in our database.

We have language bindings in Shell, Ruby, Python, JavaScript, C# and Java! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

<!-- This example API documentation page was created with [Slate](https://github.com/slatedocs/slate). Feel free to edit it and use it as a base for your own API's documentation. -->

<!-- # Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

RexRetail uses API keys to allow access to the API. You can register a new RexRetail API key at our [developer portal](https://rexretail-africa-web-sandbox.accelerexholdings.com/login).

RexRetail expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Bearer: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside> -->

# Identity

## Login

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl -X POST "https://rexretail-africa-sandbox.accelerexholdings.com/api/accelerex-ecr/user-management/v1/identity/login" 
-H  "accept: application/json" 
-H  "Authorization: Bearer meowmeowmeow" 
-H  "Content-Type: application/json" 
-d "{\"username\":\"string\",\"password\":\"string\",\"tokenExpireAt\":0,\"merchant\":\"string\"}"
```

```javascript
const data = {
  "username": "string",
  "password": "string",
  "tokenExpireAt": 0,
  "merchant": "string"
};

fetch('https://rexretail-africa-sandbox.accelerexholdings.com/api/accelerex-ecr/user-management/v1/identity/login', {
  method: 'POST', // or 'PUT'
  headers: {
    'Content-Type': 'application/json',
  },
  body: JSON.stringify(data),
})
.then(response => response.json())
.then(data => {
  console.log('Success:', data);
})
.catch((error) => {
  console.error('Error:', error);
});

```

> The above command returns JSON structured like this:

```json
{
    "jsonWebToken": {
        "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIzOTkiLCJpc3MiOiJhY2NlbGVyZXguZWNyLnNlcnZpY2UiLCJpYXQiOjE2NDkxNDUxNDYsImV4cCI6MTY0OTIzMTU0NiwidW5pcXVlX25hbWUiOiIzOTkiLCJhdWQiOiJhY2NlbGVyZXguZWNyLnNlcnZpY2UifQ.ifz2H2Qxu-kCNr3s2N0j5avRCR3Lota3RJtqzvSd34o",
        "refreshToken": "AQAAAAEAACcQAAAAEEt5fcscijhrLOMjlrf8yglqy9Oj1aZyv2Ko30tI631Zq2wsTOdaSxXO3CRQ2izA",
        "expires": 1649231546
    },
    "userDetails": {
        "roleCategory": "SuperAdmin",
        "userRole": "SystemAdministrator",
        "permissions": [
            "CAN_MANAGE_PERMISSION",
            "CAN_VIEW_PERMISSION",
            "CAN_MANAGE_ROLE",
            "CAN_VIEW_ROLE",
            "CAN_VIEW_ROLES",
            "CAN_MANAGE_SUBSCRIPTION",
            "CAN_VIEW_SUBSCRIPTION",
            "CAN_SEARCH_SUBSCRIPTION",
            "CAN_CREATE_MERCHANT",
            "CAN_UPDATE_MERCHANT",
            "CAN_VIEW_MERCHANT",
            "CAN_VIEW_ALL_MERCHANT",
            "CAN_SEARCH_MERCHANT",
            "CAN_VIEW_ALL_MERCHANTS_BILL",
            "CAN_UPDATE_ALL_MERCHANT",
            "CAN_UPDATE_ALL_MERCHANT_SUBSCRIPTION",
            "CAN_CREATE_ALL_MERCHANTS_BILL",
            "CAN_VIEW_ALL_SETTLEMENT",
            "CAN_VIEW_ALL_CATEGORIES",
            "CAN_VIEW_ALL_CUSTOMERS",
            "CAN_UPDATE_DISPUTE",
            "CAN_RESOLVE_DISPUTE",
            "CAN_VIEW_DISPUTE",
            "CAN_VIEW_ALL_DISPUTES",
            "CAN_SEARCH_ALL_DISPUTES",
            "CAN_UPDATE_ALL_USER",
            "CAN_UPDATE_USER_EMAIL",
            "CAN_UPDATE_USER_PHONENUMBER",
            "CAN_UPDATE_USER_ROLE",
            "CAN_VIEW_ALL_USER",
            "CAN_SEARCH_ALL_USER",
            "CAN_CREATE_ALL_USER",
            "CAN_MANAGE_DEVICE",
            "CAN_VIEW_DEVICE",
            "CAN_VIEW_ALL_DEVICES",
            "CAN_REASSIGN_DEVICE",
            "CAN_ADD_ANY_DEVICE",
            "CAN_VIEW_ALL_STORES",
            "CAN_VIEW_ALL_ORDERS",
            "CAN_VIEW_ALL_PRODUCTS",
            "CAN_VIEW_ADMIN_REPORT",
            "CAN_VIEW_ALL_INVENTORY",
            "CAN_VIEW_AUDIT_LOGS",
            "CAN_MANAGE_ANP",
            "CAN_VIEW_POS_REQUEST_THRESHOLD",
            "CAN_UPDATE_POS_REQUEST_THRESHOLD",
            "CAN_VIEW_ALL_POS_REQUESTS",
            "CAN_VIEW_ALL_MERCHANTS_POS_BILL",
            "CAN_CREATE_ALL_MERCHANTS_POS_BILL",
            "CAN_MANAGE_POS_PLAN",
            "CAN_VIEW_POS_PLAN",
            "CAN_SEARCH_POS_PLAN",
            "CAN_UPDATE_SPECIAL_USER_INFO"
        ],
        "phoneNumber": "2348080801116",
        "firstName": "Taiwo16",
        "lastName": "OJO116",
        "active": true,
        "activatedOn": "2022-03-19T21:22:01.17573Z",
        "merchant": {
            "address": "Kwabenya Accra",
            "activatedOn": "2022-03-19T21:21:28.098917Z",
            "accountNumber": "1199999999",
            "accountName": "Fidelity Bank",
            "bankCode": "0009",
            "name": "OJO SHOP 16",
            "code": "SH-216-GH",
            "contactEmail": "taiwotherock16@gmail.com",
            "contactPhoneNumber": "+2348080801116",
            "currency": "NGN",
            "subscriptionPlan": "Standard",
            "subscriptionStatus": "InActive",
            "startDate": "2022-03-24T21:21:28.100444Z",
            "nextPaymentDate": "2022-03-24T21:21:28.100444Z",
            "lastPaymentDate": null,
            "active": true,
            "logoUrl": "",
            "currentSubscriptionPlan": {
                "name": "Standard",
                "fee": 2,
                "maxNumberOfStores": 5,
                "maxNumberOfUsers": 5,
                "maxNumberOfPOSDevices": 5,
                "maxNumberOfOtherDevices": 5,
                "paymentCycle": "Monthly",
                "trialPeriodDays": 5,
                "type": "outright",
                "active": true,
                "id": 1,
                "createdOn": "2020-09-14T22:36:57.944083Z",
                "updatedOn": "2021-08-26T18:36:12.012084Z"
            },
            "cycleLength": 2,
            "totalCycles": 0,
            "totalPayment": 0,
            "paymentCycle": "Monthly",
            "cacNumber": "NG00000789",
            "natureOfBusiness": "Trading",
            "taxIdentificationNumber": "",
            "bankVerificationNumber": null,
            "id": 575,
            "createdOn": "2022-03-19T21:21:28.616822Z",
            "updatedOn": "2022-03-19T22:04:08.788431Z"
        },
        "currentStore": null,
        "email": "taiwo.ojo@accelerexholdings.com",
        "lastLogin": "2022-04-05T07:36:08.345451Z",
        "username": "bankadmin",
        "id": 399,
        "createdOn": "2022-03-19T21:22:01.315745Z",
        "updatedOn": "2022-04-05T07:36:08.409073Z"
    },
    "hasCompletedOnBoarding": false,
    "invoiceViewModel": {
        "amount": 25,
        "merchant": "OJO SHOP 16",
        "reference": "0001010100b7467b7",
        "paymentStatus": "Pending",
        "dueDate": "2022-03-24T21:21:28.100444Z",
        "nextRun": "2022-03-19T21:32:52.681378Z",
        "periodStart": "2022-03-24T21:21:28.100444Z",
        "periodEnd": "2022-07-24T21:21:28.100444Z",
        "auto": true,
        "paymentMethod": null,
        "paymentDate": null,
        "maskedCardNumber": null,
        "cardHolderName": null,
        "stan": null,
        "authCode": null,
        "retrievalRefNumber": null,
        "responseCode": null,
        "responseDescription": null,
        "providerReference": null,
        "retryCount": 0,
        "subscriptionName": "Standard",
        "quantity": 2,
        "status": "Open",
        "id": 435,
        "createdOn": "2022-03-19T21:32:53.0691Z",
        "updatedOn": null
    }
}
```

This endpoint enables login for GA administrators and merchant admins.

### HTTP Request

`POST https://rexretail-africa-sandbox.accelerexholdings.com/api/accelerex-ecr/user-management/v1/identity/login`

<!-- ### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted. -->

<aside class="success">
Login Successful!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -X DELETE \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

