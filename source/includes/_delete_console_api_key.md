## Delete Console API Key

> Example of request for deleting console's API key:

```javascript
{
	type: 'delete_console_api_key',
	console_id: '-Bjasf8234l',
	bundle: {
		api_key: '231d5833-4734-4652-9d8c-64295437f4e5'
	}
}
```

Deletes an existing console's API key and drops access to REST API using this key.

**Request parameters**

Parameter  | Required | Description
-----------|----------|------------
type | YES | `'delete_console_api_key'`
bundle.api_key | YES | API key

> Example of response after deleting console's API key:

```javascript
{
	request_id: '-L72HL9asdK',
	status: 'success'
}
```

**Response parameters**

Parameter  | Description
-----------|------------
status | operation status: if it was successfull - `'success'`, otherwise  - `'failure'`

**Modified endpoints**

Endpoint  | Description
-----------|------------
`/consoles/[console_id]/api_keys` | deletes key from console API keys
`/consoles_api_keys` | removes mapping to console ID by API key
