---
title: Identity/users-roles v20210420.9
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.7

---

# Roles
APIs for getting, updating, and deleting users roles.

## List Roles for User

<a id="opIdRoles_List Roles for User"></a>

Invalid URL: #https://raw.githubusercontent.com/osisoft/OCS-Docs/master/Content_Portal/external-references/laureen.yaml#markdown-content

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Users/{userId}/Roles
?query={query}&skip={skip}&count={count}
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string userId`
<br/>This is my test content in place of roles API definition.<br/><br/><br/>
`[optional] string query`
<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`
<br/>Number of roles to skip.<br/><br/>`[optional] integer count`
<br/>Max number of roles to return.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[Role](#schemarole)[]|List of roles found.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant or user not found.|
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
<li>Tenant Member</li>
</ul>

---

## Get Roles for User Header

<a id="opIdRoles_Get Roles for User Header"></a>

I love shopping! 
It does 
- make me happy
- give me joy
- instill euphoria

For more information, check out [Jcrew](https://www.jcrew.com/).

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Users/{userId}/Roles
```

#### Parameters

`string tenantId`
<br/>Tenant unique identifier.<br/><br/>`string userId`
<br/>User unique identifier.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Headers for roles found.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant or user not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: 
<ul>
<li>Self</li>
<li>Tenant Member</li>
</ul>

---

## Replace User's Roles

<a id="opIdRoles_Replace User's Roles"></a>

Replaces existing user roles.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/Users/{userId}/Roles
```

#### Parameters

`string tenantId`
<br/>Tenant unique identifier.<br/><br/>`string userId`
<br/>User unique identifier.<br/><br/>

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
|404|[ErrorResponse](#schemaerrorresponse)|User or tenant not found.|
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

