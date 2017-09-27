## Create Console API Key

> Example of console's API key creation request:

```javascript
{
	type: 'create_console_apikey',
	console_id: '-Bjasf8234l'
}
```

Creates a new API key for existing console to get access to REST API.

**Request parameters**

Parameter  | Required | Description
-----------|----------|------------
type | YES | `'create_console_api_key'`

> Example of response for creation console's API key:

```javascript
{
	request_id: '-HG72Kjaye',
	api_key: '231d5833-4734-4652-9d8c-64295437f4e5'
}
```

**Response parameters**

Parameter  | Description
-----------|------------
api_key | created API key

> Example of modified endpoints after processed console's API key creation request:

```javascript
consoles: {
	'-Bjasf8234l': {
		api_keys: {
			'231d5833-4734-4652-9d8c-64295437f4e5': true
		}
	}
},
consoles_api_keys: {
	'231d5833-4734-4652-9d8c-64295437f4e5': '-Bjasf8234l'
}
```

**Modified endpoints**

Endpoint  | Description
-----------|------------
`/consoles/[console_id]/api_keys` | adds a new key to console instance
`/consoles_api_keys` | adds mapping to console ID by API key
