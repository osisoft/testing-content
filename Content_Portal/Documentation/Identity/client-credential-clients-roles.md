---
title: Identity/client-credential-clients-roles v20210313.4
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.6

---

[[_TOC_]]

# Roles
APIs for getting, updating, and deleting client credential client roles.

## List Client Credential Client Roles All

<a id="opIdRoles_List Client Credential Client Roles All"></a>

Returns a list of roles for the specified client credential client.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Roles
?query={query}&skip={skip}&count={count}
```

### Parameters

`string tenantId`
<br/>Tenant unique identifier.<br/><br/>`string clientId`
<br/>Client credential client unique identifier.<br/><br/>
`[optional] string query`
<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`
<br/>Number of roles to skip.<br/><br/>`[optional] integer count`
<br/>Max number of roles to return.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[Role](#schemarole)[]|List of client credential client roles.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant or client credential client not found.|
|408|[ErrorResponse](#schemaerrorresponse)|None|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
> 200 Response

```json
[
  {
    "Id": "string",
    "Name": "string",
    "Description": "string",
    "RoleScope": 1,
    "TenantId": "string",
    "CommunityId": "string",
    "RoleTypeId": "string"
  }
]
```

### Authorization

Allowed for these roles: 
<ul>
<li>Self</li>
<li>Tenant Administrator</li>
</ul>

---

## Get Client Credential Client Roles Header

<a id="opIdRoles_Get Client Credential Client Roles Header"></a>

Head request to get the total number of client credential client roles for the specified client credential client.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Roles

```

### Parameters

`string tenantId`
<br/>Tenant unique identifier.<br/><br/>`string clientId`
<br/>Client credential client unique identifier.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for specified client credential client roles.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant or client credential client not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: 
<ul>
<li>Self</li>
<li>Tenant Administrator</li>
</ul>

---

## Put Client Credential Client Roles All

<a id="opIdRoles_Put Client Credential Client Roles All"></a>

Replaces existing client credential client roles.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Roles

```

### Parameters

`string tenantId`
<br/>Tenant unique identifier.<br/><br/>`string clientId`
<br/>Client credential client unique identifier.<br/><br/>

### Request Body

Update roles list.<br/>

```json
[
  {
    "Id": "string",
    "Name": "string",
    "Description": "string",
    "RoleScope": 1,
    "TenantId": "string",
    "CommunityId": "string",
    "RoleTypeId": "string"
  }
]
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[Role](#schemarole)[]|No content.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing preferences.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client credential client or tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
> 200 Response

```json
[
  {
    "Id": "string",
    "Name": "string",
    "Description": "string",
    "RoleScope": 1,
    "TenantId": "string",
    "CommunityId": "string",
    "RoleTypeId": "string"
  }
]
```

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Administrator</li>
</ul>

---

## List Client Credential Client Roles

<a id="opIdRoles_List Client Credential Client Roles"></a>

Returns a list of roles for the specified client credential client.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Clients/{clientId}/Roles
?query={query}&skip={skip}&count={count}
```

### Parameters

`string tenantId`
<br/>Tenant unique identifier.<br/><br/>`string clientId`
<br/>Client credential client unique identifier.<br/><br/>
`[optional] string query`
<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`
<br/>Number of roles to skip.<br/><br/>`[optional] integer count`
<br/>Max number of roles to return.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[Role](#schemarole)[]|List of client credential client roles.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant or client credential client not found.|
|408|[ErrorResponse](#schemaerrorresponse)|None|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
> 200 Response

```json
[
  {
    "Id": "string",
    "Name": "string",
    "Description": "string",
    "RoleScope": 1,
    "TenantId": "string",
    "CommunityId": "string",
    "RoleTypeId": "string"
  }
]
```

### Authorization

Allowed for these roles: 
<ul>
<li>Self</li>
<li>Tenant Administrator</li>
</ul>

---

## Get Client Credential Client Roles Header2

<a id="opIdRoles_Get Client Credential Client Roles Header2"></a>

Head request to get the total number of client credential client roles for the specified client credential client.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Clients/{clientId}/Roles

```

### Parameters

`string tenantId`
<br/>Tenant unique identifier.<br/><br/>`string clientId`
<br/>Client credential client unique identifier.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for specified client credential client roles.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant or client credential client not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: 
<ul>
<li>Self</li>
<li>Tenant Administrator</li>
</ul>

---

## Put Client Credential Client Roles

<a id="opIdRoles_Put Client Credential Client Roles"></a>

Replaces existing client credential client roles.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/Clients/{clientId}/Roles

```

### Parameters

`string tenantId`
<br/>Tenant unique identifier.<br/><br/>`string clientId`
<br/>Client credential client unique identifier.<br/><br/>

### Request Body

Update roles list.<br/>

```json
[
  {
    "Id": "string",
    "Name": "string",
    "Description": "string",
    "RoleScope": 1,
    "TenantId": "string",
    "CommunityId": "string",
    "RoleTypeId": "string"
  }
]
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[Role](#schemarole)[]|No content.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing preferences.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client credential client or tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
> 200 Response

```json
[
  {
    "Id": "string",
    "Name": "string",
    "Description": "string",
    "RoleScope": 1,
    "TenantId": "string",
    "CommunityId": "string",
    "RoleTypeId": "string"
  }
]
```

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Administrator</li>
</ul>

---
# Definitions

## Role

<a id="schemarole"></a>
<a id="schema_Role"></a>
<a id="tocSrole"></a>
<a id="tocsrole"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|RoleScope|[RoleScope](#schemarolescope)|false|true|None|
|TenantId|guid|false|true|None|
|CommunityId|guid|false|true|None|
|RoleTypeId|guid|false|true|None|

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "RoleScope": 1,
  "TenantId": "string",
  "CommunityId": "string",
  "RoleTypeId": "string"
}

```

---

## RoleScope

<a id="schemarolescope"></a>
<a id="schema_RoleScope"></a>
<a id="tocSrolescope"></a>
<a id="tocsrolescope"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Account|1|
|Community|2|
|Cluster|3|

---

## ErrorResponse

<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

Object returned whenever there is an error.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|true|false|Gets or sets operationId of action that caused the Error.|
|Error|string|true|false|Gets or sets error description.|
|Reason|string|true|false|Gets or sets reason for the Error.|
|Resolution|string|true|false|Gets or sets what can be done to resolve the Error.|

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "property1": null,
  "property2": null
}

```

---

