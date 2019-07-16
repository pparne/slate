--- 

title: Discover Account Servicing API 

language_tabs: 
   - shell 

toc_footers: 
   - <a href='#'>Sign Up for a Developer Key</a> 
   - <a href='https://github.com/lavkumarv'>Documentation Powered by lav</a> 

includes: 
   - errors 

search: true 

--- 

# Introduction 

API for Discover Account's transactions 

**Version:** 1.0.0 

# /ERROR
## ***GET*** 

**Summary:** error

### HTTP Request 
`***GET*** /error` 

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |

## ***POST*** 

**Summary:** error

### HTTP Request 
`***POST*** /error` 

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 201 | Created |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |

## ***PUT*** 

**Summary:** error

### HTTP Request 
`***PUT*** /error` 

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 201 | Created |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |

## ***DELETE*** 

**Summary:** error

### HTTP Request 
`***DELETE*** /error` 

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 204 | No Content |
| 401 | Unauthorized |
| 403 | Forbidden |

## ***OPTIONS*** 

**Summary:** error

### HTTP Request 
`***OPTIONS*** /error` 

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 204 | No Content |
| 401 | Unauthorized |
| 403 | Forbidden |

## ***PATCH*** 

**Summary:** error

### HTTP Request 
`***PATCH*** /error` 

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 204 | No Content |
| 401 | Unauthorized |
| 403 | Forbidden |

# /V1/TRANSACTIONS
## ***GET*** 

**Summary:** View all Transactions

### HTTP Request 
`***GET*** /v1/transactions` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| sort | query | sort | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |

## ***POST*** 

**Summary:** Save a transaction

### HTTP Request 
`***POST*** /v1/transactions` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| transaction | body | transaction | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Successfully created transaction |
| 400 | No transaction found with ID #id |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |

# /V1/TRANSACTIONS/{ID}
## ***GET*** 

**Summary:** View details of a specific transaction

### HTTP Request 
`***GET*** /v1/transactions/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id | path | id | Yes | long |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Successfully retrieved transaction |
| 400 | No transaction found with ID #id |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |

## ***PUT*** 

**Summary:** Update details of a specific transaction

### HTTP Request 
`***PUT*** /v1/transactions/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id | path | id | Yes | long |
| transaction | body | transaction | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Successfully updated transaction |
| 400 | No transaction found with ID #id |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |

## ***DELETE*** 

**Summary:** Delete a specific transaction

### HTTP Request 
`***DELETE*** /v1/transactions/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id | path | id | Yes | long |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Successfully updated transaction |
| 204 | No Content |
| 400 | No transaction found with ID #id |
| 401 | Unauthorized |
| 403 | Forbidden |

<!-- Converted with the swagger-to-slate https://github.com/lavkumarv/swagger-to-slate -->
