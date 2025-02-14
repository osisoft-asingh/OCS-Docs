---
uid: community-roles

---

# Roles
Cluster APIs for getting community roles

## `List instanced Roles for a Community`

<a id="opIdCommunityRoles_List instanced Roles for a Community"></a>

Get community roles associated with a specific community

<h3>Request</h3>

```text 
GET /api/v1-preview/Communities/{communityId}/Roles
?query={query}&skip={skip}&count={count}
```

<h4>Parameters</h4>

`string communityId`
<br/>Community identifier<br/><br/>
`[optional] string query`
<br/>(not supported) Search string identifier<br/><br/>`[optional] integer skip`
<br/>Parameter representing the zero-based offset of the first object to retrieve. If unspecified, a default value of 0 is used.<br/><br/>`[optional] integer count`
<br/>Parameter representing the maximum number of objects to retrieve. If unspecified, a default value of 100 is used.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Role](#schemarole)[]|Set of community roles (type `Role`) associated with the community ( `communityId`)|
|400|[ErrorResponse](#schemaerrorresponse)|Bad request|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error|

<h4>Example response body</h4>

> 200 Response ([Role](#schemarole)[])

```json
[
  {
    "Id": "string",
    "Name": "string",
    "Description": "string",
    "RoleScope": 0,
    "TenantId": "string",
    "CommunityId": "string",
    "RoleTypeId": "string"
  }
]
```

<h3>Authorization</h3>

Allowed for these roles: 
<ul>
<li>Community Member</li>
<li>Tenant Administrator</li>
</ul>

---
## Definitions

### Role

<a id="schemarole"></a>
<a id="schema_Role"></a>
<a id="tocSrole"></a>
<a id="tocsrole"></a>

Object for retrieving a role

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|Role identifier. Generated by the server upon creation.|
|Name|string|false|true|Role name. This cannot be empty.|
|Description|string|false|true|Role description|
|RoleScope|[RoleScope](#schemarolescope)|false|true|Role scope|
|TenantId|string|false|true|Tenant identifier, if this is a Tenant Role. Otherwise, set to null.|
|CommunityId|string|false|true|Community identifier, if this is a Community Role. Otherwise set to null.|
|RoleTypeId|string|false|true|Role type identifier for built-in roles|

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "RoleScope": 0,
  "TenantId": "string",
  "CommunityId": "string",
  "RoleTypeId": "string"
}

```

---

### RoleScope

<a id="schemarolescope"></a>
<a id="schema_RoleScope"></a>
<a id="tocSrolescope"></a>
<a id="tocsrolescope"></a>

The object that represents the scope of a given role

<h4>Enumerated Values</h4>

|Property|Value|
|---|---|
|None|0|
|Tenant|1|
|Community|2|
|Cluster|3|

---

### ErrorResponse

<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

Object returned whenever there is an error

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|true|false|Operation identifier of action that caused the error|
|Error|string|true|false|Error description|
|Reason|string|true|false|Reason for the error|
|Resolution|string|true|false|Resolution to resolve the error|
|DynamicProperties|object|false|true|Additional properties|

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "DynamicProperties": {
    "property1": null,
    "property2": null
  },
  "property1": null,
  "property2": null
}

```

---

