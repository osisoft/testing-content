---
title: Identity/claims v20210305.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="identity-claims-claims">Claims</h1>

	

	

	

	

---
## List Identity Provider Claims

<a id="opIdClaims_List Identity Provider Claims"></a>

Gets all identity provider claims for an identity provider on a tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Claims
```

<h3 id="claims_list-identity-provider-claims-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string identityProviderId`<br/>Identity provider unique identifier.<br/><br/>
`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of identity providers to skip.<br/><br/>`[optional] integer count`<br/>Maximum number of identity providers to return.<br/><br/>

<h3 id="claims_list-identity-provider-claims-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderClaim](#schemaidentityproviderclaim)[]|List of identity provider claims found.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant or identity provider not found.|
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
## Get Identity Provider Claims Header

<a id="opIdClaims_Get Identity Provider Claims Header"></a>

Gets header for all identity provider claims for an identity provider on a tenant.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Claims
```

<h3 id="claims_get-identity-provider-claims-header-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string identityProviderId`<br/>Identity provider unique identifier.<br/><br/>

<h3 id="claims_get-identity-provider-claims-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Identity provider claim header information.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant or identity provider not found.|
|500|None|Internal server error.|

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Post Identity Provider Claim

<a id="opIdClaims_Post Identity Provider Claim"></a>

Creates a new identity provider claim for an identity provider on a tenant.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Claims
```

### Request Body

Identity provider claim to create.<br/>

```json
{
  "Value": "string",
  "IdentityProviderClaimTypeNameId": "string",
  "RoleIds": [
    "string"
  ]
}
```

<h3 id="claims_post-identity-provider-claim-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string identityProviderId`<br/>Identity provider unique identifier.<br/><br/>

<h3 id="claims_post-identity-provider-claim-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[IdentityProviderClaim](#schemaidentityproviderclaim)|Identity provider claim created.|
|302|None|Found.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant, identity provider, or roles not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|409|[ErrorResponse](#schemaerrorresponse)|Identity provider claim configuration already exists.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 201 Response

```json
{
  "Id": "string",
  "TypeName": "string",
  "Value": "string",
  "RoleIds": [
    "string"
  ]
}
```

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Identity Provider Claim

<a id="opIdClaims_Get Identity Provider Claim"></a>

Gets an identity provider claim from an identity provider on a tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Claims/{identityProviderClaimId}
```

<h3 id="claims_get-identity-provider-claim-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string identityProviderId`<br/>Identity provider unique identifier.<br/><br/>`string identityProviderClaimId`<br/>Identity provider claim unique identifier.<br/><br/>

<h3 id="claims_get-identity-provider-claim-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderClaim](#schemaidentityproviderclaim)|Identity provider claim specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant, identity provider, or identity provider claim not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Id": "string",
  "TypeName": "string",
  "Value": "string",
  "RoleIds": [
    "string"
  ]
}
```

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Identity Provider Claim Header

<a id="opIdClaims_Get Identity Provider Claim Header"></a>

Gets an identity provider claim header from an identity provider on a tenant.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Claims/{identityProviderClaimId}
```

<h3 id="claims_get-identity-provider-claim-header-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string identityProviderId`<br/>Identity provider unique identifier.<br/><br/>`string identityProviderClaimId`<br/>Identity provider claim unique identifier.<br/><br/>

<h3 id="claims_get-identity-provider-claim-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Identity provider claim specified header.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant, identity provider, or identity provider claim not found.|
|500|None|Internal server error.|

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Put Identity Provider Claim

<a id="opIdClaims_Put Identity Provider Claim"></a>

Creates a new identity provider claim for an identity provider on a tenant.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Claims/{identityProviderClaimId}
```

### Request Body

Updated identity provider claim values.<br/>

```json
{
  "Value": "string",
  "RoleIds": [
    "string"
  ]
}
```

<h3 id="claims_put-identity-provider-claim-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string identityProviderId`<br/>Identity provider unique identifier.<br/><br/>`string identityProviderClaimId`<br/>Identity provider claim unique identifier.<br/><br/>

<h3 id="claims_put-identity-provider-claim-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderClaim](#schemaidentityproviderclaim)|Updated identity provider claim.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant, identity provider, identity provider claim, or roles not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|409|[ErrorResponse](#schemaerrorresponse)|Identity provider claim configuration already exists.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Id": "string",
  "TypeName": "string",
  "Value": "string",
  "RoleIds": [
    "string"
  ]
}
```

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Delete Identity Provider Claim

<a id="opIdClaims_Delete Identity Provider Claim"></a>

Deletes an identity provider claim for an identity provider on a tenant.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Claims/{identityProviderClaimId}
```

<h3 id="claims_delete-identity-provider-claim-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string identityProviderId`<br/>Identity provider unique identifier.<br/><br/>`string identityProviderClaimId`<br/>Identity provider claim unique identifier.<br/><br/>

<h3 id="claims_delete-identity-provider-claim-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant, identity provider, or identity provider claim not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 401 Response

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

<h2 id="tocS_IdentityProviderClaim">IdentityProviderClaim</h2>

<a id="schemaidentityproviderclaim"></a>
<a id="schema_IdentityProviderClaim"></a>
<a id="tocSidentityproviderclaim"></a>
<a id="tocsidentityproviderclaim"></a>

```json
{
  "Id": "string",
  "TypeName": "string",
  "Value": "string",
  "RoleIds": [
    "string"
  ]
}

```

Object representing a claim from an identity provider to map to a role.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|Identity provider claim unique identifier.|
|TypeName|string|false|true|Type name for this identity provider claim.|
|Value|string|false|true|Value for this identity provider claim.|
|RoleIds|string[]|false|true|List of role Ids that this claim on this identity provider will map to.|

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

<h2 id="tocS_IdentityProviderClaimCreate">IdentityProviderClaimCreate</h2>

<a id="schemaidentityproviderclaimcreate"></a>
<a id="schema_IdentityProviderClaimCreate"></a>
<a id="tocSidentityproviderclaimcreate"></a>
<a id="tocsidentityproviderclaimcreate"></a>

```json
{
  "Value": "string",
  "IdentityProviderClaimTypeNameId": "string",
  "RoleIds": [
    "string"
  ]
}

```

Identity provider claim to create.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Value|string|false|true|Value for this identity provider claim.|
|IdentityProviderClaimTypeNameId|guid|false|false|Identity provider claim type name unique identifier for this identity provider claim.|
|RoleIds|string[]|false|true|List of role Ids associated with this identity provider claim.|

<h2 id="tocS_IdentityProviderClaimUpdate">IdentityProviderClaimUpdate</h2>

<a id="schemaidentityproviderclaimupdate"></a>
<a id="schema_IdentityProviderClaimUpdate"></a>
<a id="tocSidentityproviderclaimupdate"></a>
<a id="tocsidentityproviderclaimupdate"></a>

```json
{
  "Value": "string",
  "RoleIds": [
    "string"
  ]
}

```

Update information for an identity provider claim.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Value|string|false|true|Value for this identity provider claim.|
|RoleIds|string[]|false|true|List of role Ids associated with this identity provider claim.|

