---
title: Identity/communities-invitations v20210311.2
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

# Invitations
Defines the public API endpoints that are used to manage community invitations. Using this API you can, for example, create, retrieve, update and process invitations. You can also resend an invitation email.

## Process Invitation2

<a id="opIdInvitations_Process Invitation2"></a>

Processes an action against a particular community invitation. The available actions include accept, decline and resend.

### Request
```text 
PUT /api/v1/community/invitations/{invitationId}

```

Tenant Administrator is Authorized for this API along with Community Administrator because a Tenant Administrator is allowed to Accept or Decline an Invitation.
Community Administrator is allowed to resend Invitations.

### Request Body

The invitation action.<br/>

```json
{
  "Action": "Accept"
}
```

### Parameters

`string invitationId`
<br/>The id of the invitation.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Created. The invitation was processed.|
|202|None|Accepted. The invitation action was processed and the notification accepted.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The requested item was not found.|
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

## Get Invitation Details2

<a id="opIdInvitations_Get Invitation Details2"></a>

Gets details for a community invitation.

### Request
```text 
GET /api/v1/community/invitations/{invitationId}/details

```

This API has no Community permissions as this API will be used by the UI during the Invitation Acceptance process.
This API will be used to present relevant information to the caller (Community Name, Id, etc.) so the caller can 
make an informed choice about what invitation they are accepting. 
Only Tenant Administrators can accept a Community Invitation, so this API allows Tenant Administrators.

### Parameters

`string invitationId`
<br/>The id of the invitation.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[CommunityInvitationDetails](#schemacommunityinvitationdetails)|The `CommunityInvitationDetails`.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The requested item was not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Request Timeout. The request has timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

#### Example response body
> 200 Response

```json
{
  "CommunityName": "string",
  "CommunityId": "string",
  "TenantAlreadyMemberOfCommunity": true,
  "InvitationState": "None"
}
```

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Administrator</li>
</ul>

---

## Process Invitation

<a id="opIdInvitations_Process Invitation"></a>

Processes an action against a particular community invitation. The available actions include accept, decline and resend.

### Request
```text 
PUT /api/v1/communityinvitations/{invitationId}

```

Tenant Administrator is Authorized for this API along with Community Administrator because a Tenant Administrator is allowed to Accept or Decline an Invitation.
Community Administrator is allowed to resend Invitations.

### Request Body

The invitation action.<br/>

```json
{
  "Action": "Accept"
}
```

### Parameters

`string invitationId`
<br/>The id of the invitation.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Created. The invitation was processed.|
|202|None|Accepted. The invitation action was processed and the notification accepted.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The requested item was not found.|
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

## Get Invitation Details

<a id="opIdInvitations_Get Invitation Details"></a>

Gets details for a community invitation.

### Request
```text 
GET /api/v1/communityinvitations/{invitationId}/details

```

This API has no Community permissions as this API will be used by the UI during the Invitation Acceptance process.
This API will be used to present relevant information to the caller (Community Name, Id, etc.) so the caller can 
make an informed choice about what invitation they are accepting. 
Only Tenant Administrators can accept a Community Invitation, so this API allows Tenant Administrators.

### Parameters

`string invitationId`
<br/>The id of the invitation.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[CommunityInvitationDetails](#schemacommunityinvitationdetails)|The `CommunityInvitationDetails`.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The requested item was not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Request Timeout. The request has timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

#### Example response body
> 200 Response

```json
{
  "CommunityName": "string",
  "CommunityId": "string",
  "TenantAlreadyMemberOfCommunity": true,
  "InvitationState": "None"
}
```

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Administrator</li>
</ul>

---

## List Community Invitations By Issuing Tenant And Community

<a id="opIdInvitations_List Community Invitations By Issuing Tenant And Community"></a>

Get Invitations associated with a specific issuing Tenant and Community.

### Request
```text 
GET /api/v1/tenants/{tenantId}/communities/{communityId}/invitations
?query={query}&skip={skip}&count={count}
```

### Parameters

`string tenantId`
<br/>The identifier of the issuing Tenant. Tenant must belong to the Community.<br/><br/>`string communityId`
<br/>The identifier of the Community the recipient of the Invitation is being invited to.<br/><br/>
`[optional] string query`
<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`
<br/>Number of records to skip.<br/><br/>`[optional] integer count`
<br/>Maximum number of records to return.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[CommunityInvitation](#schemacommunityinvitation)[]|Set of Invitations (Type `CommunityInvitation`) associated with the issuing Tenant ( `tenantId`) and Community ( `communityId`).|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The requested item was not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Request Timeout. The request has timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

#### Example response body
> 200 Response

```json
[
  {
    "Id": "string",
    "Issued": "2019-08-24T14:15:22Z",
    "Expires": "2019-08-24T14:15:22Z",
    "Accepted": "2019-08-24T14:15:22Z",
    "State": "None",
    "IssuingTenantId": "string",
    "InvitedTenantId": "string",
    "CommunityId": "string",
    "CommunityName": "string",
    "InvitationRecipient": "string",
    "CommunityModeratorRecipients": [
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

## Create Community Invitation

<a id="opIdInvitations_Create Community Invitation"></a>

Creates a community invitation for a specific community.

### Request
```text 
POST /api/v1/tenants/{tenantId}/communities/{communityId}/invitations

```

### Request Body

The invitation to create.<br/>

```json
{
  "InvitationRecipient": "string",
  "CommunityModeratorRecipients": [
    "string"
  ]
}
```

### Parameters

`string tenantId`
<br/>The id of the owning tenant.<br/><br/>`string communityId`
<br/>The id of the community.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|201|[CommunityInvitation](#schemacommunityinvitation)|Returns the created invitation of type `CommunityInvitation`.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The requested item was not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Request Timeout. The request has timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

#### Example response body
> 201 Response

```json
{
  "Id": "string",
  "Issued": "2019-08-24T14:15:22Z",
  "Expires": "2019-08-24T14:15:22Z",
  "Accepted": "2019-08-24T14:15:22Z",
  "State": "None",
  "IssuingTenantId": "string",
  "InvitedTenantId": "string",
  "CommunityId": "string",
  "CommunityName": "string",
  "InvitationRecipient": "string",
  "CommunityModeratorRecipients": [
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

## Get Community Invitation By Id

<a id="opIdInvitations_Get Community Invitation By Id"></a>

Gets a community invitation by id.

### Request
```text 
GET /api/v1/tenants/{tenantId}/communities/{communityId}/invitations/{invitationId}

```

### Parameters

`string tenantId`
<br/>The tenant id.<br/><br/>`string communityId`
<br/>The id of the community.<br/><br/>`string invitationId`
<br/>The id of the invitation.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[CommunityInvitation](#schemacommunityinvitation)|Returns the invitation of type `CommunityInvitation`.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The requested item was not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Request Timeout. The request has timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

#### Example response body
> 200 Response

```json
{
  "Id": "string",
  "Issued": "2019-08-24T14:15:22Z",
  "Expires": "2019-08-24T14:15:22Z",
  "Accepted": "2019-08-24T14:15:22Z",
  "State": "None",
  "IssuingTenantId": "string",
  "InvitedTenantId": "string",
  "CommunityId": "string",
  "CommunityName": "string",
  "InvitationRecipient": "string",
  "CommunityModeratorRecipients": [
    "string"
  ]
}
```

### Authorization

Allowed for these roles: 
<ul>
<li>Community Member</li>
<li>Tenant Administrator</li>
</ul>

---

## Delete Community Invitation

<a id="opIdInvitations_Delete Community Invitation"></a>

Deletes a community invitation by invitation id.

### Request
```text 
DELETE /api/v1/tenants/{tenantId}/communities/{communityId}/invitations/{invitationId}

```

### Parameters

`string tenantId`
<br/>The tenant id.<br/><br/>`string communityId`
<br/>The id of the community.<br/><br/>`string invitationId`
<br/>The id of the invitation.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No Content. The invitation has been deleted.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The requested item was not found.|
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

## List Accepted Community Invitations By Invited Tenant

<a id="opIdInvitations_List Accepted Community Invitations By Invited Tenant"></a>

Get Invitations associated with a specific invited Tenant. Only Invitations in the Accepted state are returned. By using this call you can then determine the Communities to which a Tenant has been invited via the returned CommunityInvitation.CommunityId attribute.

### Request
```text 
GET /api/v1/tenants/{tenantId}/communityinvitations
?query={query}&skip={skip}&count={count}
```

### Parameters

`string tenantId`
<br/>The id of the invited tenant.<br/><br/>
`[optional] string query`
<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`
<br/>Number of records to skip.<br/><br/>`[optional] integer count`
<br/>Maximum number of records to return.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[CommunityInvitation](#schemacommunityinvitation)[]|Set of Accepted Invitations (Type `CommunityInvitation`) associated with the issuing Tenant ( `tenantId`).|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The requested item was not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Request Timeout. The request has timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

#### Example response body
> 200 Response

```json
[
  {
    "Id": "string",
    "Issued": "2019-08-24T14:15:22Z",
    "Expires": "2019-08-24T14:15:22Z",
    "Accepted": "2019-08-24T14:15:22Z",
    "State": "None",
    "IssuingTenantId": "string",
    "InvitedTenantId": "string",
    "CommunityId": "string",
    "CommunityName": "string",
    "InvitationRecipient": "string",
    "CommunityModeratorRecipients": [
      "string"
    ]
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

## CommunityInvitation

<a id="schemacommunityinvitation"></a>
<a id="schema_CommunityInvitation"></a>
<a id="tocScommunityinvitation"></a>
<a id="tocscommunityinvitation"></a>

The Community Invitation Output Data Transfer Object.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|Gets or sets unique Invitation Id.|
|Issued|date-time|false|false|Gets or sets Invitation issuing timestamp.|
|Expires|date-time|false|false|Gets or sets Invitation expiration timestamp.|
|Accepted|date-time|false|true|Gets or sets Invitation accepted timestamp.|
|State|[CommunityInvitationState](#schemacommunityinvitationstate)|false|false|Gets or sets Invitation state.|
|IssuingTenantId|guid|false|false|Gets or sets ID of the Tenant that issued the Invitation.|
|InvitedTenantId|guid|false|true|Gets or sets ID of the Tenant that is invited.|
|CommunityId|guid|false|false|Gets or sets ID of the Community whom the Invitation was issued to.|
|CommunityName|string|false|true|Gets or sets name of the Community for which the Invitation was issued.|
|InvitationRecipient|string|false|true|Gets or sets the email address of the recipient that shall be notified to accept the Invitation.|
|CommunityModeratorRecipients|string[]|false|true|Gets or sets the list of email addresses of recipients that shall be notified to confirm the invited Tenant.|

```json
{
  "Id": "string",
  "Issued": "2019-08-24T14:15:22Z",
  "Expires": "2019-08-24T14:15:22Z",
  "Accepted": "2019-08-24T14:15:22Z",
  "State": "None",
  "IssuingTenantId": "string",
  "InvitedTenantId": "string",
  "CommunityId": "string",
  "CommunityName": "string",
  "InvitationRecipient": "string",
  "CommunityModeratorRecipients": [
    "string"
  ]
}

```

---

## CommunityInvitationState

<a id="schemacommunityinvitationstate"></a>
<a id="schema_CommunityInvitationState"></a>
<a id="tocScommunityinvitationstate"></a>
<a id="tocscommunityinvitationstate"></a>

Enum for Community invitation state.

#### Enumerated Values

|Property|Value|
|---|---|
|None|None|
|InvitationCreated|InvitationCreated|
|InvitationAccepted|InvitationAccepted|
|InvitationDeclined|InvitationDeclined|
|InvitationExpired|InvitationExpired|
|InvitationCompleted|InvitationCompleted|

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

## CreateInvitationInput

<a id="schemacreateinvitationinput"></a>
<a id="schema_CreateInvitationInput"></a>
<a id="tocScreateinvitationinput"></a>
<a id="tocscreateinvitationinput"></a>

The input object to Create Invitation.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|InvitationRecipient|string|false|true|The email address of the invitation recipient.|
|CommunityModeratorRecipients|string[]|false|true|The email addresses of the Community Moderators who can confirm the Invitation.|

```json
{
  "InvitationRecipient": "string",
  "CommunityModeratorRecipients": [
    "string"
  ]
}

```

---

## CommunityInvitationDetails

<a id="schemacommunityinvitationdetails"></a>
<a id="schema_CommunityInvitationDetails"></a>
<a id="tocScommunityinvitationdetails"></a>
<a id="tocscommunityinvitationdetails"></a>

Summary of a Community Invitation.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|CommunityName|string|false|true|Gets or sets the Name of the Community.|
|CommunityId|guid|false|false|Gets or sets the Id of the Community.|
|TenantAlreadyMemberOfCommunity|boolean|false|false|Gets or sets whether the invited Tenant is already part of the Community.|
|InvitationState|[CommunityInvitationState](#schemacommunityinvitationstate)|false|false|Gets or sets the Invitation State.|

```json
{
  "CommunityName": "string",
  "CommunityId": "string",
  "TenantAlreadyMemberOfCommunity": true,
  "InvitationState": "None"
}

```

---

## ProcessInvitationInput

<a id="schemaprocessinvitationinput"></a>
<a id="schema_ProcessInvitationInput"></a>
<a id="tocSprocessinvitationinput"></a>
<a id="tocsprocessinvitationinput"></a>

The input object to Process Invitation.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Action|[ProcessInvitationAction](#schemaprocessinvitationaction)|false|false|Action to take on Invitation.|

```json
{
  "Action": "Accept"
}

```

---

## ProcessInvitationAction

<a id="schemaprocessinvitationaction"></a>
<a id="schema_ProcessInvitationAction"></a>
<a id="tocSprocessinvitationaction"></a>
<a id="tocsprocessinvitationaction"></a>

Enum for actions taken on Community Invitations.

#### Enumerated Values

|Property|Value|
|---|---|
|Accept|Accept|
|Decline|Decline|
|Resend|Resend|

---
