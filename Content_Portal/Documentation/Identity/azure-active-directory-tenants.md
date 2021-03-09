---
title: Identity/azure-active-directory-tenants v20210308.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="identity-azure-active-directory-tenants-azure-active-directory-tenants">Azure Active Directory Tenants</h1>

The model for an AAD tenant in Identity Storage.

|Name|Type|Description|
|---|---|---|
|Id|string|AAD tenant unique identifier.|
|ConsentState|[ConsentState](#schemaconsentstate)|Consent state of AAD tenant. Can be: NotConsented (0), Consented (1).|
|Domain|string|AAD tenant domain name.|

	

	

	

	

---
## List Aad Tenants For Tenant

<a id="opIdAzureActiveDirectoryTenants_List Aad Tenants For Tenant"></a>

Get all Azure Active Directory Tenants from an OSIsoft Cloud Services Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants
```

<h3 id="azureactivedirectorytenants_list-aad-tenants-for-tenant-parameters">Parameters</h3>

`string tenantId`<br/>Id of OSIsoft Cloud Services Tenant.<br/><br/>
`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of Azure Active Directory tenants to skip.<br/><br/>`[optional] integer count`<br/>Maximum number of Azure Active Directory tenants to return.<br/><br/>

<h3 id="azureactivedirectorytenants_list-aad-tenants-for-tenant-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AzureActiveDirectoryTenant](#schemaazureactivedirectorytenant)[]|List of AzureActiveDirectoryTenants found.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|or|
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

---
## Get Aad Tenants Header For Tenant

<a id="opIdAzureActiveDirectoryTenants_Get Aad Tenants Header For Tenant"></a>

Return total number of Azure Active Directory tenants in a OSIsoft Cloud Services Tenant. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants
```

<h3 id="azureactivedirectorytenants_get-aad-tenants-header-for-tenant-parameters">Parameters</h3>

`string tenantId`<br/>Id of OSIsoft Cloud Services Tenant.<br/><br/>

<h3 id="azureactivedirectorytenants_get-aad-tenants-header-for-tenant-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Headers for AzureActiveDirectoryTenants found.|
|400|None|Missing or invalid inputs.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|OSIsoft Cloud Services Tenant not found.|
|500|None|Internal server error.|

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Aad Tenant For Tenant

<a id="opIdAzureActiveDirectoryTenants_Get Aad Tenant For Tenant"></a>

Get Azure Active Directory Tenant from an OSIsoft Cloud Services Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants/{aadTenantId}
```

<h3 id="azureactivedirectorytenants_get-aad-tenant-for-tenant-parameters">Parameters</h3>

`string tenantId`<br/>Id of OSIsoft Cloud Services Tenant.<br/><br/>`string aadTenantId`<br/>Id of Azure Active Directory Tenant.<br/><br/>

<h3 id="azureactivedirectorytenants_get-aad-tenant-for-tenant-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AzureActiveDirectoryTenant](#schemaazureactivedirectorytenant)|AzureActiveDirectory specified.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|OSIsoft Cloud Services Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Id": "string",
  "ConsentState": 0,
  "Domain": "string"
}
```

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Aad Tenant Header For Tenant

<a id="opIdAzureActiveDirectoryTenants_Get Aad Tenant Header For Tenant"></a>

Validate that Azure Active Directory Tenant exists in this OSIsoft Cloud Services Tenant. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants/{aadTenantId}
```

<h3 id="azureactivedirectorytenants_get-aad-tenant-header-for-tenant-parameters">Parameters</h3>

`string tenantId`<br/>Id of OSIsoft Cloud Services Tenant.<br/><br/>`string aadTenantId`<br/>Id of Azure Active Directory Tenant.<br/><br/>

<h3 id="azureactivedirectorytenants_get-aad-tenant-header-for-tenant-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for specified Azure Active Directory Tenant.|
|400|None|Missing or invalid inputs.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|OSIsoft Cloud Services Tenant not found.|
|500|None|Internal server error.|

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Add Aad Tenant To Tenant

<a id="opIdAzureActiveDirectoryTenants_Add Aad Tenant To Tenant"></a>

Add an Azure Active Directory Tenant to the OSIsoft Cloud Services Tenant.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants/{aadTenantId}
```

<h3 id="azureactivedirectorytenants_add-aad-tenant-to-tenant-parameters">Parameters</h3>

`string tenantId`<br/>Id of OSIsoft Cloud Services Tenant.<br/><br/>`string aadTenantId`<br/>Id or Domain Name of Azure Active Directory Tenant.<br/><br/>

<h3 id="azureactivedirectorytenants_add-aad-tenant-to-tenant-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[AzureActiveDirectoryTenant](#schemaazureactivedirectorytenant)|AzureActiveDirectoryTenant object created.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|OSIsoft Cloud Services Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|409|[ErrorResponse](#schemaerrorresponse)|Id of Azure Active Directory Tenant. is already in use on the specified Tenant.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 201 Response

```json
{
  "Id": "string",
  "ConsentState": 0,
  "Domain": "string"
}
```

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Remove Aad Tenant From Tenant

<a id="opIdAzureActiveDirectoryTenants_Remove Aad Tenant From Tenant"></a>

Removal of Azure Active Directory Tenant from an OSIsoft Cloud Services Tenant is not supported.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants/{aadTenantId}
```

<h3 id="azureactivedirectorytenants_remove-aad-tenant-from-tenant-parameters">Parameters</h3>

`string tenantId`<br/>Id of OSIsoft Cloud Services Tenant.<br/><br/>`string aadTenantId`<br/>Id of Azure Active Directory Tenant to remove.<br/><br/>

<h3 id="azureactivedirectorytenants_remove-aad-tenant-from-tenant-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|NotSupportedException.|

### Example response body

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Send Aad Tenant Consent Request

<a id="opIdAzureActiveDirectoryTenants_Send Aad Tenant Consent Request"></a>

Send consent for an Azure Active Directory Tenant. OSIsoft Cloud Services needs to be granted permission to interact with the Azure Active Directory tenant. Otherwise, users from this Azure Active Directory Tenant cannot accept invitations from OSIsoft Cloud Services and log in. You can read more about this [here](https://pisquare.osisoft.com/docs/DOC-3986-msa-consent-for-azure-active-directory).

### Request
```text 
POST /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants/{aadTenantId}/SendConsent
```

### Request Body

ConsentInformation object.<br/>

```json
{
  "AzureActiveDirectoryConsentEmail": "user@example.com",
  "AzureActiveDirectoryConsentGivenName": "string",
  "AzureActiveDirectoryConsentSurname": "string",
  "AzureActiveDirectoryTenant": "string",
  "AzureActiveDirectoryConsentTypes": "string"
}
```

<h3 id="azureactivedirectorytenants_send-aad-tenant-consent-request-parameters">Parameters</h3>

`string tenantId`<br/>Id of OSIsoft Cloud Services Tenant.<br/><br/>`string aadTenantId`<br/>Id of Azure Active Directory Tenant.<br/><br/>

<h3 id="azureactivedirectorytenants_send-aad-tenant-consent-request-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|OSIsoft Cloud Services Tenant not found.|
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

<h2 id="tocS_AzureActiveDirectoryTenant">AzureActiveDirectoryTenant</h2>

<a id="schemaazureactivedirectorytenant"></a>
<a id="schema_AzureActiveDirectoryTenant"></a>
<a id="tocSazureactivedirectorytenant"></a>
<a id="tocsazureactivedirectorytenant"></a>

```json
{
  "Id": "string",
  "ConsentState": 0,
  "Domain": "string"
}

```

The model for an AAD tenant in Identity Storage.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|AAD tenant unique identifier.|
|ConsentState|[ConsentState](#schemaconsentstate)|false|false|Consent state of AAD tenant. Can be: NotConsented (0), Consented (1).|
|Domain|string|false|true|AAD tenant domain name.|

<h2 id="tocS_ConsentState">ConsentState</h2>

<a id="schemaconsentstate"></a>
<a id="schema_ConsentState"></a>
<a id="tocSconsentstate"></a>
<a id="tocsconsentstate"></a>

AAD Tenant Consent State.

#### Enumerated Values

|Property|Value|
|---|---|
|NotConsented|0|
|Consented|1|

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

<h2 id="tocS_ConsentInformation">ConsentInformation</h2>

<a id="schemaconsentinformation"></a>
<a id="schema_ConsentInformation"></a>
<a id="tocSconsentinformation"></a>
<a id="tocsconsentinformation"></a>

```json
{
  "AzureActiveDirectoryConsentEmail": "user@example.com",
  "AzureActiveDirectoryConsentGivenName": "string",
  "AzureActiveDirectoryConsentSurname": "string",
  "AzureActiveDirectoryTenant": "string",
  "AzureActiveDirectoryConsentTypes": "string"
}

```

Information about the recipient of the Azure Active Directory consent email.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|AzureActiveDirectoryConsentEmail|email|false|true|Email address to send consent.|
|AzureActiveDirectoryConsentGivenName|string|false|true|Preferred name to use in the consent email.|
|AzureActiveDirectoryConsentSurname|string|false|true|Preferred surname to use in the consent email.|
|AzureActiveDirectoryTenant|string|false|true|AAD tenant domain name (for example, mydomain.onmicrosoft.com).|
|AzureActiveDirectoryConsentTypes|string|false|true|Semicolon delimited AAD consent types. Can be "SignIn" or "SignIn;ReadAllUsersGroups".|

