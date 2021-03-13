---
title: Identity/communities-users v20210312.5
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

# Users
APIs for getting, updating, and deleting Users from Communities.

## List Community Users For Tenant

<a id="opIdUsers_List Community Users For Tenant"></a>

Get a list of Users of a Tenant in a Community.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Communities/{communityId}/Users

```

### Parameters

`string tenantId`
<br/>Id of the Tenant that belongs to this Community.<br/><br/>`string communityId`
<br/>Id of Community.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[User](#schemauser)[]|Success.|
|400|[ErrorResponse](#schemaerrorresponse)|BadRequest.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Community roles not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
> 200 Response

```json
[
  {
    "Id": "string",
    "GivenName": "string",
    "Surname": "string",
    "Name": "string",
    "Email": "string",
    "ContactEmail": "string",
    "ContactGivenName": "string",
    "ContactSurname": "string",
    "ExternalUserId": "string",
    "IdentityProviderId": "string",
    "RoleIds": [
      "string"
    ]
  }
]
```

### Authorization

Allowed for these roles: 
<ul>
<li>Community Member</li>
<li>Tenant Administrator</li>
</ul>

---

## Get Community Users Count For Tenant

<a id="opIdUsers_Get Community Users Count For Tenant"></a>

Get the count of Users of the Tenant in this Community. This endpoint is identical to the `Guid)` endpoint except it does not return a body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Communities/{communityId}/Users

```

### Parameters

`string tenantId`
<br/>Id of the calling Tenant that belongs to this Community.<br/><br/>`string communityId`
<br/>Id of Community.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Success.|
|400|[ErrorResponse](#schemaerrorresponse)|BadRequest.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Community roles not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
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

Allowed for these roles: 
<ul>
<li>Community Member</li>
<li>Tenant Administrator</li>
</ul>

---

## Add User To Community

<a id="opIdUsers_Add User To Community"></a>

Add a user to a Community.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/Communities/{communityId}/Users/{userId}

```

### Parameters

`string tenantId`
<br/>Id of the Tenant that belongs to this Community<br/><br/>`string communityId`
<br/>Id of Community.<br/><br/>`string userId`
<br/>Id of the User to add to the specified Community.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|201|[User](#schemauser)|Created.|
|400|[ErrorResponse](#schemaerrorresponse)|BadRequest.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
> 201 Response

```json
{
  "Id": "string",
  "GivenName": "string",
  "Surname": "string",
  "Name": "string",
  "Email": "string",
  "ContactEmail": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ExternalUserId": "string",
  "IdentityProviderId": "string",
  "RoleIds": [
    "string"
  ]
}
```

### Authorization

Allowed for these roles: 
<ul>
<li>Community Administrator</li>
<li>Community Moderator</li>
<li>Tenant Administrator</li>
</ul>

---

## Remove User From Community

<a id="opIdUsers_Remove User From Community"></a>

Remove a User from a Community.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/Communities/{communityId}/Users/{userId}

```

### Parameters

`string tenantId`
<br/>Id of the Tenant that belongs to this Community.<br/><br/>`string communityId`
<br/>Id of Community.<br/><br/>`string userId`
<br/>Id of the user to remove from the specified Community.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|204|None|Removed.|
|400|[ErrorResponse](#schemaerrorresponse)|BadRequest.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
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

Allowed for these roles: 
<ul>
<li>Community Administrator</li>
<li>Community Moderator</li>
<li>Tenant Administrator</li>
</ul>

---
# Definitions

## User

<a id="schemauser"></a>
<a id="schema_User"></a>
<a id="tocSuser"></a>
<a id="tocsuser"></a>

Object for retrieving a user.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|User unique identifier.|
|GivenName|string|false|true|Given name of the user.|
|Surname|string|false|true|Surname of the user.|
|Name|string|false|true|Name of the user.|
|Email|string|false|true|Email of the user.|
|ContactEmail|string|false|true|Contact email for the user. User will only be contacted through this email.|
|ContactGivenName|string|false|true|Preferred contact name for the user.|
|ContactSurname|string|false|true|Preferred contact surname for the user.|
|ExternalUserId|string|false|true|Provider unique identifier for the user. This is the unique identifier we get from the identity provider.|
|IdentityProviderId|guid|false|true|Identity provider unique identifier used to authenticate the user. Will be set once the user accepts an invitation. If not specified when sending the invitation to the user, it can be any of the identity provider Ids configured for this tenant.|
|RoleIds|string[]|false|true|List of roles to be assigned to this client. Member role is always required. For security reasons we advise against assigning administrator role to a client.|

```json
{
  "Id": "string",
  "GivenName": "string",
  "Surname": "string",
  "Name": "string",
  "Email": "string",
  "ContactEmail": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ExternalUserId": "string",
  "IdentityProviderId": "string",
  "RoleIds": [
    "string"
  ]
}

```

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

