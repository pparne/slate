---
title: Discover Account Servicing API
language_tabs:
  - java: Java
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<h1 id="discover-account-servicing-api">Discover Account Servicing API v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

API for Discover Account's transactions

Base URLs:

* <a href="//localhost:3000/">//localhost:3000/</a>

Email: <a href="mailto:noone@nowhere.com">Dont' Contact me!</a> Web: <a href="https://dontcontactme.nooneexits/about/">Dont' Contact me!</a> 

<h1 id="discover-account-servicing-api-transaction-controller">transaction-controller</h1>

Transaction Controller

## View all Transactions

<a id="opIdgetAllTransactionsUsingGET"></a>

> Code samples

```java
URL obj = new URL("/localhost:3000/v1/transactions");
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

`GET /v1/transactions`

<h3 id="view-all-transactions-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|sort|query|string|false|sorting order|

> Example responses

> 200 Response

```json
{}
```

<h3 id="view-all-transactions-responses">Responses</h3>

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

# Schemas

<h2 id="tocSiterable">Iterable</h2>

<a id="schemaiterable"></a>

```json
{}

```

*Iterable*

### Properties

*None*

<h2 id="tocSstacktraceelement">StackTraceElement</h2>

<a id="schemastacktraceelement"></a>

```json
{
  "className": "string",
  "fileName": "string",
  "lineNumber": 0,
  "methodName": "string",
  "nativeMethod": true
}

```

*StackTraceElement*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|className|string|false|none|none|
|fileName|string|false|none|none|
|lineNumber|integer(int32)|false|none|none|
|methodName|string|false|none|none|
|nativeMethod|boolean|false|none|none|

<h2 id="tocSthrowable">Throwable</h2>

<a id="schemathrowable"></a>

```json
{
  "cause": null,
  "localizedMessage": "string",
  "message": "string",
  "stackTrace": [
    {
      "className": "string",
      "fileName": "string",
      "lineNumber": 0,
      "methodName": "string",
      "nativeMethod": true
    }
  ],
  "suppressed": [
    null
  ]
}

```

*Throwable*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|cause|[Throwable](#schemathrowable)|false|none|none|
|localizedMessage|string|false|none|none|
|message|string|false|none|none|
|stackTrace|[[StackTraceElement](#schemastacktraceelement)]|false|none|none|
|suppressed|[[Throwable](#schemathrowable)]|false|none|none|

<h2 id="tocStransaction">Transaction</h2>

<a id="schematransaction"></a>

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

*Transaction*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int64)|false|none|none|
|lastModified|string(date-time)|false|none|none|
|merchantName|string|false|none|none|
|transactionAmount|number(double)|false|none|none|
|transactionDate|string(date-time)|false|none|none|
|userId|integer(int64)|false|none|none|

<h2 id="tocStransactiondoesnotexistexception">TransactionDoesNotExistException</h2>

<a id="schematransactiondoesnotexistexception"></a>

```json
{
  "cause": {
    "cause": null,
    "localizedMessage": "string",
    "message": "string",
    "stackTrace": [
      {
        "className": "string",
        "fileName": "string",
        "lineNumber": 0,
        "methodName": "string",
        "nativeMethod": true
      }
    ],
    "suppressed": [
      null
    ]
  },
  "localizedMessage": "string",
  "message": "string",
  "stackTrace": [
    {
      "className": "string",
      "fileName": "string",
      "lineNumber": 0,
      "methodName": "string",
      "nativeMethod": true
    }
  ],
  "suppressed": [
    {
      "cause": null,
      "localizedMessage": "string",
      "message": "string",
      "stackTrace": [
        {
          "className": "string",
          "fileName": "string",
          "lineNumber": 0,
          "methodName": "string",
          "nativeMethod": true
        }
      ],
      "suppressed": [
        null
      ]
    }
  ]
}

```

*TransactionDoesNotExistException*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|cause|[Throwable](#schemathrowable)|false|none|none|
|localizedMessage|string|false|none|none|
|message|string|false|none|none|
|stackTrace|[[StackTraceElement](#schemastacktraceelement)]|false|none|none|
|suppressed|[[Throwable](#schemathrowable)]|false|none|none|

