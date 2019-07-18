---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell: Shell
  - json: JSON
toc_footers: []
includes: []
search: true
---

# Introduction

The Discover Transactions API allows you to retrieve all transaction data and specific transactions for Discover customers who have authorization to use the application. It also allows you to update, delete, and create transactions for these authorized users. In most cases, users will want to see all their transactions, which will return a full list of transactions in the database for the authorized user. Users can also request a specific transaction, and the Transactions API will return just that requested transaction. For each transaction, the following data will be retrieved for the user: transaction date, merchant name, transaction amount, and if there were any changes made to the transaction, a modified date..

The Discover Transactions API is organized around REST. In order to request information, the API uses HTTP methods, which can read, create, update, and delete information. The API is resource-oriented, accepts form-encoded request bodies, and responds to HTTP requests in JSON format.

# Authentication

For the purposes of this Proof of Concept, there is no authentication measure in place.

# Transactions

## Get All Transactions

```shell
curl "http://localhost:3000/v1/transactions"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "lastModified": "2019-07-17T19:14:39Z",
    "merchantName": "string",
    "transactionAmount": 20.35,
    "transactionDate": "2019-07-17T19:14:39Z",
    "userId": 101
  },
  {
    "id": 2,
    "lastModified": "2019-07-17T19:14:39Z",
    "merchantName": "string",
    "transactionAmount": 8.34,
    "transactionDate": "2019-07-17T19:14:39Z",
    "userId": 101
  }
]
```

This endpoint retrieves all Transactions.

### HTTP Request

`GET /v1/transactions`

### Query Parameters

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|sort|query|string|false|sorting order|

> Example responses

> 200 Response

```json
[
  {
    "id": 1,
    "lastModified": "2019-07-17T19:14:39Z",
    "merchantName": "string",
    "transactionAmount": 20.35,
    "transactionDate": "2019-07-17T19:14:39Z",
    "userId": 101
  },
  {
    "id": 2,
    "lastModified": "2019-07-17T19:14:39Z",
    "merchantName": "string",
    "transactionAmount": 8.34,
    "transactionDate": "2019-07-17T19:14:39Z",
    "userId": 101
  }
]
```

## Responses

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Iterable](#schemaiterable)|

<aside class="success">
This operation does not require authentication
</aside>

## Save a transaction

<a id="opIdsaveTransactionUsingPOST"></a>

> Code samples

```java
URL obj = new URL("/localhost:3000/v1/transactions");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /v1/transactions`

> Body parameter

```json
{
  "id": 0,
  "lastModified": "2019-07-17T19:14:39Z",
  "merchantName": "string",
  "transactionAmount": 0,
  "transactionDate": "2019-07-17T19:14:39Z",
  "userId": 0
}
```

<h3 id="save-a-transaction-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Transaction](#schematransaction)|false|Transaction to save|

> Example responses

> 201 Response

```json
{
  "id": 0,
  "lastModified": "2019-07-17T19:14:39Z",
  "merchantName": "string",
  "transactionAmount": 0,
  "transactionDate": "2019-07-17T19:14:39Z",
  "userId": 0
}
```

<h3 id="save-a-transaction-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Successfully created transaction|[Transaction](#schematransaction)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|No transaction found with #id|[TransactionDoesNotExistException](#schematransactiondoesnotexistexception)|

<aside class="success">
This operation does not require authentication
</aside>

## Get transaction

<a id="opIdgetTransactionUsingGET"></a>

> Code samples

```java
URL obj = new URL("/localhost:3000/v1/transactions/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`GET /v1/transactions/{id}`

<h3 id="get-transaction-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer(int64)|true|Transaction Identifier|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "lastModified": "2019-07-17T19:14:39Z",
  "merchantName": "string",
  "transactionAmount": 0,
  "transactionDate": "2019-07-17T19:14:39Z",
  "userId": 0
}
```

<h3 id="get-transaction-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successfully retrieved transaction|[Transaction](#schematransaction)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|No transaction found with #id|[TransactionDoesNotExistException](#schematransactiondoesnotexistexception)|

<aside class="success">
This operation does not require authentication
</aside>

## Update details of a specific transaction

<a id="opIdupdateTransactionUsingPUT"></a>

> Code samples

```java
URL obj = new URL("/localhost:3000/v1/transactions/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`PUT /v1/transactions/{id}`

> Body parameter

```json
{
  "id": 0,
  "lastModified": "2019-07-17T19:14:39Z",
  "merchantName": "string",
  "transactionAmount": 0,
  "transactionDate": "2019-07-17T19:14:39Z",
  "userId": 0
}
```

<h3 id="update-details-of-a-specific-transaction-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer(int64)|true|Transaction Id that needs to be updated|
|body|body|[Transaction](#schematransaction)|false|Transaction with updated info|

> Example responses

> 201 Response

```json
{
  "id": 0,
  "lastModified": "2019-07-17T19:14:39Z",
  "merchantName": "string",
  "transactionAmount": 0,
  "transactionDate": "2019-07-17T19:14:39Z",
  "userId": 0
}
```

<h3 id="update-details-of-a-specific-transaction-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Successfully updated transaction|[Transaction](#schematransaction)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|No transaction found with ID #id|None|

<aside class="success">
This operation does not require authentication
</aside>

## Delete a specific transaction

<a id="opIddeleteTransactionUsingDELETE"></a>

> Code samples

```java
URL obj = new URL("/localhost:3000/v1/transactions/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`DELETE /v1/transactions/{id}`

<h3 id="delete-a-specific-transaction-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer(int64)|true|Identifier of transaction that is being deleted.|

<h3 id="delete-a-specific-transaction-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successfully updated transaction|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|No transaction found with ID #id|None|

<aside class="success">
This operation does not require authentication
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
curl "http://example.com/api/kittens/2"
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
curl "http://example.com/api/kittens/2"
  -X DELETE
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

