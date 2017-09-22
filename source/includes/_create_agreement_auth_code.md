## Create Agreement Auth Code

> Example of agreement's auth code creation request:

```javascript
{
	type: 'create_agreement_auth_code',
	console_id: '-Bjasf8234l',
	bundle: {
		agreement_id: '-KuYrIw65D3'
	}
}
```

Creates a new auth code for existing console's agreement.

**Request parameters**

Parameter  | Required | Description
-----------|----------|------------
type | YES | `'create_agreement_auth_code'`
bundle.agreement_id | YES | agreement ID

> Example of response for creation agreement's auth code:

```javascript
{
	request_id: '-Jhr7u32lk',
	auth_code: '73376d6a-e457-4a66-b06a-c16a637cfa4b'
}
```

**Response parameters**

Parameter  | Description
-----------|------------
auth_code | created auth code

> Example of modified endpoints after processed agreement's auth code creation request:

```javascript
agreements: {
	'-KuYrIw65D3': {
		auth_codes: {
			'73376d6a-e457-4a66-b06a-c16a637cfa4b': {
				active: true
			}
		}
	}
}
```

**Modified endpoints**

Endpoint  | Description
-----------|------------
`/agreements/[agreement_id]/auth_codes` | adds a new auth code to agreement instance
