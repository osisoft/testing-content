---
title: Identity/communities v20210420.3
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.7

---

# Communities
A Community is an organizational entity that facilitates data sharing across multiple Tenants.

## List Communities a Tenant is joined to

<a id="opIdCommunities_List Communities a Tenant is joined to"></a>

Gets all communities a tenant is joined to.

### Request
```text 
GET /api/v1/tenants/{tenantId}/Communities
```

#### Parameters

`string tenantId`
<br/>X Dave identifier <br/><br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[Community](#schemacommunity)[]|Returns the current communities for the tenant. This is a set of objects of type `Community`.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request.|
|401|None|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|408|[ErrorResponse](#schemaerrorresponse)|Request Timeout. The request has timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

#### Example response body
> 200 Response

```json
[
  {
    "Id": "string",
    "Name": "string",
    "Alias": "string",
    "Description": "string",
    "Tenants": [
      {
        "Id": "string",
        "Name": "string",
        "Status": "Undefined",
        "IsOwner": true,
        "UserCount": 0,
        "ClientCount": 0
      }
    ],
    "DateCreated": "2019-08-24T14:15:22Z",
    "StreamsContributedCount": 0,
    "TotalStreamsContributedCount": 0
  }
]
```

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## Create a new Community

<a id="opIdCommunities_Create a new Community"></a>

### Request
```text 
POST /api/v1/tenants/{tenantId}/Communities
```

#### Parameters

`string tenantId`
<br/><br/>

### Request Body

X Josh identifier <br/><br/>

```json
{
  "Name": "string",
  "Description": "string"
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|201|[Community](#schemacommunity)|Returns the created community of type `Community`.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|408|[ErrorResponse](#schemaerrorresponse)|Request Timeout. The request has timed out.|
|409|[ErrorResponse](#schemaerrorresponse)|None|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

#### Example response body
> 201 Response

```json
{
  "Id": "string",
  "Name": "string",
  "Alias": "string",
  "Description": "string",
  "Tenants": [
    {
      "Id": "string",
      "Name": "string",
      "Status": "Undefined",
      "IsOwner": true,
      "UserCount": 0,
      "ClientCount": 0
    }
  ],
  "DateCreated": "2019-08-24T14:15:22Z",
  "StreamsContributedCount": 0,
  "TotalStreamsContributedCount": 0
}
```

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Administrator</li>
</ul>

---

## Get a Community by Id

<a id="opIdCommunities_Get a Community by Id"></a>

OCS has wonderful documentation. 
It does 
- a
- b
- c
For more information see [documentation](https://ocs-docs.osisoft.com/Content_Portal/Documentation/Management/Account_ServiceBlog.html#get-service-blog-entry).

### Request
```text 
GET /api/v1/tenants/{tenantId}/Communities/{communityId}
```

#### Parameters

`string tenantId`
<br/><br/>`string communityId`
<br/>X Mark identifier <br/><br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[Community](#schemacommunity)|Returns the current communities for the tenant. This is a set of objects of type `Community`.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request.|
|401|None|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|408|[ErrorResponse](#schemaerrorresponse)|Request Timeout. The request has timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

#### Example response body
> 200 Response

```json
{
  "Id": "string",
  "Name": "string",
  "Alias": "string",
  "Description": "string",
  "Tenants": [
    {
      "Id": "string",
      "Name": "string",
      "Status": "Undefined",
      "IsOwner": true,
      "UserCount": 0,
      "ClientCount": 0
    }
  ],
  "DateCreated": "2019-08-24T14:15:22Z",
  "StreamsContributedCount": 0,
  "TotalStreamsContributedCount": 0
}
```

### Authorization

Allowed for these roles: 
<ul>
<li>Community Member</li>
<li>Tenant Administrator</li>
</ul>

---

## Update Community Info

<a id="opIdCommunities_Update Community Info"></a>

Updates attributes of a community such as name and description.

### Request
```text 
PUT /api/v1/tenants/{tenantId}/Communities/{communityId}
```

#### Parameters

`string tenantId`
<br/>The id of the owning tenant.<br/><br/>`string communityId`
<br/>The id of the community.<br/><br/>

### Request Body

The community object that contains the attributes to use for the update.<br/>

```json
{
  "Name": "string",
  "Description": "string"
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Success. The community tenant was updated.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The requested community tenant was not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Request Timeout. The request has timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

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
<li>Tenant Administrator</li>
</ul>

---

## Delete a Community

<a id="opIdCommunities_Delete a Community"></a>

Deletes a community by id.

### Request
```text 
DELETE /api/v1/tenants/{tenantId}/Communities/{communityId}
```

#### Parameters

`string tenantId`
<br/>The id of the owning tenant.<br/><br/>`string communityId`
<br/>The id of the community to delete.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No Content. The community was successfully deleted.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The community was not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Request Timeout. The request has timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

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
<li>Tenant Administrator</li>
</ul>

---
# Definitions

## Community

<a id="schemacommunity"></a>
<a id="schema_Community"></a>
<a id="tocScommunity"></a>
<a id="tocscommunity"></a>

The Community Data Transfer Object. This is the model representation exposed to callers of controller endpoints.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|The Primary Key.|
|Name|string|false|true|The Name of the Community.|
|Alias|string|false|true|The requesting Tenant's alias for the Community.|
|Description|string|false|true|The Description of the Community.|
|Tenants|[[CommunityTenant](#schemacommunitytenant)]|false|true|The List of CommunityTenants that are in the Community.|
|DateCreated|date-time|false|true|The Date that the Community was created.|
|StreamsContributedCount|integer|false|false|Current Tenant's view of how many streams it contributed.|
|TotalStreamsContributedCount|integer|false|false|Total streams from all Community Tenants.|

```json
{
  "Id": "string",
  "Name": "string",
  "Alias": "string",
  "Description": "string",
  "Tenants": [
    {
      "Id": "string",
      "Name": "string",
      "Status": "Undefined",
      "IsOwner": true,
      "UserCount": 0,
      "ClientCount": 0
    }
  ],
  "DateCreated": "2019-08-24T14:15:22Z",
  "StreamsContributedCount": 0,
  "TotalStreamsContributedCount": 0
}

```

---

## CommunityTenant

<a id="schemacommunitytenant"></a>
<a id="schema_CommunityTenant"></a>
<a id="tocScommunitytenant"></a>
<a id="tocscommunitytenant"></a>

The Community Tenant Data Transfer Object.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|The Tenant ID.|
|Name|string|false|true|The name of the Tenant.|
|Status|[CommunityTenantStatus](#schemacommunitytenantstatus)|false|false|The Status of the CommunityTenant in the Community.|
|IsOwner|boolean|false|false|Boolean to indicate if CommunityTenant is Owner of Community.|
|UserCount|integer|false|false|Summary count of the users authorized to access this community within the Tenant.|
|ClientCount|integer|false|false|Summary count of the clients authorized to access this community within this Tenant.|

```json
{
  "Id": "string",
  "Name": "string",
  "Status": "Undefined",
  "IsOwner": true,
  "UserCount": 0,
  "ClientCount": 0
}

```

---

## CommunityTenantStatus

<a id="schemacommunitytenantstatus"></a>
<a id="schema_CommunityTenantStatus"></a>
<a id="tocScommunitytenantstatus"></a>
<a id="tocscommunitytenantstatus"></a>

Represents a status of a Community Tenant.

#### Enumerated Values

|Property|Value|
|---|---|
|Undefined|Undefined|
|AwaitingConfirmation|AwaitingConfirmation|
|Paused|Paused|
|Active|Active|
|Remove|Remove|

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

## CreateCommunityInput

<a id="schemacreatecommunityinput"></a>
<a id="schema_CreateCommunityInput"></a>
<a id="tocScreatecommunityinput"></a>
<a id="tocscreatecommunityinput"></a>

The CreateCommunityInput Data Transfer Object. This is the model input for the CreateCommunity controller endpoint.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Name|string|false|true|The Name of the Community to create.|
|Description|string|false|true|The Description of the Community.|

```json
{
  "Name": "string",
  "Description": "string"
}

```

---

## UpdateCommunityInput

<a id="schemaupdatecommunityinput"></a>
<a id="schema_UpdateCommunityInput"></a>
<a id="tocSupdatecommunityinput"></a>
<a id="tocsupdatecommunityinput"></a>

The UpdateCommunityInput Data Transfer Object. This is the model input for the UpdateCommunityById controller endpoint.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Name|string|false|true|The Name of the Community.|
|Description|string|false|true|The Description of the Community.|

```json
{
  "Name": "string",
  "Description": "string"
}

```

---

