---
title: Identity/client-credential-clients-roles v20210305.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="identity-client-credential-clients-roles-roles">Roles</h1>

|Name|Type|Description|
|---|---|---|
|Id|guid|None|
|Name|string|None|
|Description|string|None|
|RoleScope|[RoleScope](#schemarolescope)|None|
|TenantId|guid|None|
|CommunityId|guid|None|
|RoleTypeId|guid|None|

	

	

	

---
## List Client Credential Client Roles All

<a id="opIdRoles_List Client Credential Client Roles All"></a>

Returns a list of roles for the specified client credential client.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Roles
```

<h3 id="roles_list-client-credential-client-roles-all-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client credential client unique identifier.<br/><br/>
`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of roles to skip.<br/><br/>`[optional] integer count`<br/>Max number of roles to return.<br/><br/>

<h3 id="roles_list-client-credential-client-roles-all-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Role](#schemarole)[]|List of client credential client roles.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant or client credential client not found.|
|408|[ErrorResponse](#schemaerrorresponse)|None|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 400 Response

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

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
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

<h3 id="roles_get-client-credential-client-roles-header-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client credential client unique identifier.<br/><br/>

<h3 id="roles_get-client-credential-client-roles-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for specified client credential client roles.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant or client credential client not found.|
|500|None|Internal server error.|

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
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

<h3 id="roles_put-client-credential-client-roles-all-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client credential client unique identifier.<br/><br/>

<h3 id="roles_put-client-credential-client-roles-all-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Role](#schemarole)[]|No content.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing preferences.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client credential client or tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 400 Response

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

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
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
```

<h3 id="roles_list-client-credential-client-roles-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client credential client unique identifier.<br/><br/>
`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of roles to skip.<br/><br/>`[optional] integer count`<br/>Max number of roles to return.<br/><br/>

<h3 id="roles_list-client-credential-client-roles-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Role](#schemarole)[]|List of client credential client roles.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant or client credential client not found.|
|408|[ErrorResponse](#schemaerrorresponse)|None|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 400 Response

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

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
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

<h3 id="roles_get-client-credential-client-roles-header2-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client credential client unique identifier.<br/><br/>

<h3 id="roles_get-client-credential-client-roles-header2-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for specified client credential client roles.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant or client credential client not found.|
|500|None|Internal server error.|

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
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

<h3 id="roles_put-client-credential-client-roles-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client credential client unique identifier.<br/><br/>

<h3 id="roles_put-client-credential-client-roles-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Role](#schemarole)[]|No content.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing preferences.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client credential client or tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 400 Response

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

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

# Definitions

<h2 id="tocS_Role">Role</h2>

<a id="schemarole"></a>
<a id="schema_Role"></a>
<a id="tocSrole"></a>
<a id="tocsrole"></a>

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

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|RoleScope|[RoleScope](#schemarolescope)|false|true|None|
|TenantId|guid|false|true|None|
|CommunityId|guid|false|true|None|
|RoleTypeId|guid|false|true|None|

<h2 id="tocS_RoleScope">RoleScope</h2>

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

<h2 id="tocS_ErrorResponse">ErrorResponse</h2>

<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

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

Object returned whenever there is an error.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|true|false|Gets or sets operationId of action that caused the Error.|
|Error|string|true|false|Gets or sets error description.|
|Reason|string|true|false|Gets or sets reason for the Error.|
|Resolution|string|true|false|Gets or sets what can be done to resolve the Error.|

