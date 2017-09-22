## Assign Agreement

> Example of assign agreement request:

```javascript
{
	type: 'assign_agreement',
	console_id: '-Bjasf8234l',
	bundle: {
		agreement_id: '-KuYrIw65D3',
		auth_code: '73376d6a-e457-4a66-b06a-c16a637cfa4b',
		client_id: '-GcnvMbGIABF'
	}
}
```

Assigns own agreement to another console using agreement's auth code.

**Request parameters**

Parameter  | Required | Description
-----------|----------|------------
type | YES | `'assign_agreement'`
bundle.agreement_id | YES | agreement ID
bundle.auth_code | YES | agreement auth code
bundle.client_id | YES | client ID (i.e. console ID) to assign agreement to

> Example of response for assigning agreement:

```javascript
{
	request_id: '-DK9hO0aiwk',
	status: 'success'
}
```

**Response parameters**

Parameter  | Description
-----------|------------
status | operation status: if it was successfull - `'success'`, otherwise  - `'failure'`

> Example of modified endpoints after processed request:

```javascript
agreements: {
	'-KuYrIw65D3': {
		auth_codes: {
			'73376d6a-e457-4a66-b06a-c16a637cfa4b': {
				active: true,
				client: '-GcnvMbGIABF'
			}
		},
		auth_clients: {
			'-GcnvMbGIABF': '73376d6a-e457-4a66-b06a-c16a637cfa4b'
		}
	}
},
consoles: {
	'-GcnvMbGIABF': {
		agreements: {
			'-KuYrIw65D3': {
				active: true
			}
		}
	}
}
```

**Modified endpoints**

Endpoint  | Description
-----------|------------
`/agreements/[agreement_id]/auth_codes/[code]` | adds a reference to assigned client
`/agreements/[agreement_id]/auth_clients` | adds a assigned client record
`/consoles/[client_id]/agreements/` | adds assigned agreement reference
