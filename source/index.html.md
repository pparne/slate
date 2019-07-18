---
title: API Reference

language_tabs: []
toc_footers: []
includes: []
search: true
---

# Introduction

The Discover Transactions API allows you to retrieve all transaction data and specific transactions for Discover customers who have authorization to use the application. It also allows you to update, delete, and create transactions for these authorized users. In most cases, users will want to see all their transactions, which will return a full list of transactions in the database for the authorized user. Users can also request a specific transaction, and the Transactions API will return just that requested transaction. For each transaction, the following data will be retrieved for the user: transaction date, merchant name, transaction amount, and if there were any changes made to the transaction, a modified date..

The Discover Transactions API is organized around REST. In order to request information, the API uses HTTP methods, which can read, create, update, and delete information. The API is resource-oriented, accepts form-encoded request bodies, and responds to HTTP requests in JSON format.

# Authentication

For the purposes of this Proof of Concept, there is no authentication measure in place.

# Errors

The Discover Transactions API uses conventional HTTP response codes to indicate the success or failure of an API request.

When an action is performed on a user or a transaction that does not exist, then the user will receive a 404 Bad Request Error, which means the request was not valid usually due to a missing required parameter.

The 200 HTTP Code indicates the success of an API request.

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

Retrieves all the transactions.

### HTTP Request

`GET /v1/transactions`

### Parameters

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|sort|query|string|false|sorting order|

> Example responses

> 200 Response

### Responses

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Iterable](#schemaiterable)|

<aside class="success">
This operation does not require authentication
</aside>

## Save a transaction

### HTTP Request

`POST /v1/transactions`

Saves a new transaction in the database, given that all the parameters required are complete and valid. If a parameter is missing or invalid, then an error will be returned.

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

### Parameters

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

### Responses

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Successfully created transaction|[Transaction](#schematransaction)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|No transaction found with #id|[TransactionDoesNotExistException](#schematransactiondoesnotexistexception)|

<aside class="success">
This operation does not require authentication
</aside>

## Get transaction

When a specific transaction ID is provided, the system will retrieve the transaction specifically associated with that transaction ID. If the transaction ID is invalid, an error will be returned.

### HTTP Request

`GET /v1/transactions/{id}`

### Parameters

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

### Responses

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successfully retrieved transaction|[Transaction](#schematransaction)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|No transaction found with #id|[TransactionDoesNotExistException](#schematransactiondoesnotexistexception)|

<aside class="success">
This operation does not require authentication
</aside>

## Update details of a specific transaction

When a specific transaction ID is provided and the details of this transaction are updated, the transaction associated with the ID will be modified accordingly and a parameter called modified_date will show the last time this transaction was changed. If the specific transaction ID does not exist, then an error will be returned.

### HTTP Request

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

### Parameters

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

### Responses

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Successfully updated transaction|[Transaction](#schematransaction)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|No transaction found with ID #id|None|

<aside class="success">
This operation does not require authentication
</aside>

## Delete a specific transaction

When a specific transaction ID is provided, as long as it is valid, that transaction will be deleted from the database. If the transaction ID is invalid, an error will be returned.

### HTTP Request

`DELETE /v1/transactions/{id}`

### Parameters

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

