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

<h1 id="discover-account-servicing-api-basic-error-controller">basic-error-controller</h1>

Basic Error Controller

## error

<a id="opIderrorUsingPATCH"></a>

> Code samples

```java
URL obj = new URL("/localhost:3000/error");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
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

`PATCH /error`

> Example responses

> 200 Response

<h3 id="error-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|

<h3 id="error-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» **additionalProperties**|object|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

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
|sort|query|string|false|sort|

> Example responses

> 200 Response

```json
{}
```

<h3 id="view-all-transactions-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Iterable](#schemaiterable)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|

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
  "lastModified": "2019-07-17T13:48:15Z",
  "merchantName": "string",
  "transactionAmount": 0,
  "transactionDate": "2019-07-17T13:48:15Z",
  "userId": 0
}
```

<h3 id="save-a-transaction-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Transaction](#schematransaction)|true|transaction|

> Example responses

> 201 Response

```json
{
  "id": 0,
  "lastModified": "2019-07-17T13:48:15Z",
  "merchantName": "string",
  "transactionAmount": 0,
  "transactionDate": "2019-07-17T13:48:15Z",
  "userId": 0
}
```

<h3 id="save-a-transaction-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Successfully created transaction|[Transaction](#schematransaction)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|No transaction found with ID #id|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|

<aside class="success">
This operation does not require authentication
</aside>

## View details of a specific transaction

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

<h3 id="view-details-of-a-specific-transaction-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer(int64)|true|id|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "lastModified": "2019-07-17T13:48:15Z",
  "merchantName": "string",
  "transactionAmount": 0,
  "transactionDate": "2019-07-17T13:48:15Z",
  "userId": 0
}
```

<h3 id="view-details-of-a-specific-transaction-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successfully retrieved transaction|[Transaction](#schematransaction)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|No transaction found with ID #id|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|

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
  "lastModified": "2019-07-17T13:48:15Z",
  "merchantName": "string",
  "transactionAmount": 0,
  "transactionDate": "2019-07-17T13:48:15Z",
  "userId": 0
}
```

<h3 id="update-details-of-a-specific-transaction-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer(int64)|true|id|
|body|body|[Transaction](#schematransaction)|true|transaction|

> Example responses

> 201 Response

```json
{
  "id": 0,
  "lastModified": "2019-07-17T13:48:15Z",
  "merchantName": "string",
  "transactionAmount": 0,
  "transactionDate": "2019-07-17T13:48:15Z",
  "userId": 0
}
```

<h3 id="update-details-of-a-specific-transaction-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Successfully updated transaction|[Transaction](#schematransaction)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|No transaction found with ID #id|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|

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
|id|path|integer(int64)|true|id|

<h3 id="delete-a-specific-transaction-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successfully updated transaction|None|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|No transaction found with ID #id|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|

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

<h2 id="tocSmodelandview">ModelAndView</h2>

<a id="schemamodelandview"></a>

```json
{
  "empty": true,
  "model": {},
  "modelMap": {
    "property1": {},
    "property2": {}
  },
  "reference": true,
  "status": "100 CONTINUE",
  "view": {
    "contentType": "string"
  },
  "viewName": "string"
}

```

*ModelAndView*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|empty|boolean|false|none|none|
|model|object|false|none|none|
|modelMap|object|false|none|none|
|» **additionalProperties**|object|false|none|none|
|reference|boolean|false|none|none|
|status|string|false|none|none|
|view|[View](#schemaview)|false|none|none|
|viewName|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|100 CONTINUE|
|status|101 SWITCHING_PROTOCOLS|
|status|102 PROCESSING|
|status|103 CHECKPOINT|
|status|200 OK|
|status|201 CREATED|
|status|202 ACCEPTED|
|status|203 NON_AUTHORITATIVE_INFORMATION|
|status|204 NO_CONTENT|
|status|205 RESET_CONTENT|
|status|206 PARTIAL_CONTENT|
|status|207 MULTI_STATUS|
|status|208 ALREADY_REPORTED|
|status|226 IM_USED|
|status|300 MULTIPLE_CHOICES|
|status|301 MOVED_PERMANENTLY|
|status|302 FOUND|
|status|302 MOVED_TEMPORARILY|
|status|303 SEE_OTHER|
|status|304 NOT_MODIFIED|
|status|305 USE_PROXY|
|status|307 TEMPORARY_REDIRECT|
|status|308 PERMANENT_REDIRECT|
|status|400 BAD_REQUEST|
|status|401 UNAUTHORIZED|
|status|402 PAYMENT_REQUIRED|
|status|403 FORBIDDEN|
|status|404 NOT_FOUND|
|status|405 METHOD_NOT_ALLOWED|
|status|406 NOT_ACCEPTABLE|
|status|407 PROXY_AUTHENTICATION_REQUIRED|
|status|408 REQUEST_TIMEOUT|
|status|409 CONFLICT|
|status|410 GONE|
|status|411 LENGTH_REQUIRED|
|status|412 PRECONDITION_FAILED|
|status|413 PAYLOAD_TOO_LARGE|
|status|413 REQUEST_ENTITY_TOO_LARGE|
|status|414 URI_TOO_LONG|
|status|414 REQUEST_URI_TOO_LONG|
|status|415 UNSUPPORTED_MEDIA_TYPE|
|status|416 REQUESTED_RANGE_NOT_SATISFIABLE|
|status|417 EXPECTATION_FAILED|
|status|418 I_AM_A_TEAPOT|
|status|419 INSUFFICIENT_SPACE_ON_RESOURCE|
|status|420 METHOD_FAILURE|
|status|421 DESTINATION_LOCKED|
|status|422 UNPROCESSABLE_ENTITY|
|status|423 LOCKED|
|status|424 FAILED_DEPENDENCY|
|status|426 UPGRADE_REQUIRED|
|status|428 PRECONDITION_REQUIRED|
|status|429 TOO_MANY_REQUESTS|
|status|431 REQUEST_HEADER_FIELDS_TOO_LARGE|
|status|451 UNAVAILABLE_FOR_LEGAL_REASONS|
|status|500 INTERNAL_SERVER_ERROR|
|status|501 NOT_IMPLEMENTED|
|status|502 BAD_GATEWAY|
|status|503 SERVICE_UNAVAILABLE|
|status|504 GATEWAY_TIMEOUT|
|status|505 HTTP_VERSION_NOT_SUPPORTED|
|status|506 VARIANT_ALSO_NEGOTIATES|
|status|507 INSUFFICIENT_STORAGE|
|status|508 LOOP_DETECTED|
|status|509 BANDWIDTH_LIMIT_EXCEEDED|
|status|510 NOT_EXTENDED|
|status|511 NETWORK_AUTHENTICATION_REQUIRED|

<h2 id="tocStransaction">Transaction</h2>

<a id="schematransaction"></a>

```json
{
  "id": 0,
  "lastModified": "2019-07-17T13:48:15Z",
  "merchantName": "string",
  "transactionAmount": 0,
  "transactionDate": "2019-07-17T13:48:15Z",
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

<h2 id="tocSview">View</h2>

<a id="schemaview"></a>

```json
{
  "contentType": "string"
}

```

*View*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|contentType|string|false|none|none|

