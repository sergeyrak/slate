## Delete Agreement Auth Code

> Example of request for deleting agreement's auth code:

```javascript
{
	type: 'delete_agreement_auth_code',
	console_id: '-Bjasf8234l',
	bundle: {
		agreement_id: '-KuYrIw65D3',
		auth_code: '73376d6a-e457-4a66-b06a-c16a637cfa4b'
	}
}
```

Deletes an existing agreement's auth code. If auth code is already assigned to another console, assignment will be dropped as well.

**Request parameters**

Parameter  | Required | Description
-----------|----------|------------
type | YES | `'delete_agreement_auth_code'`
bundle.agreement_id | YES | agreement ID
bundle.auth_code | YES | auth code

> Example of response after deleting agreement's auth code:

```javascript
{
	request_id: '-Kl81faklza',
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
`/agreements/[agreement_id]/auth_codes` | deletes auth code from agreement instance
`/agreements/[agreement_id]/auth_clients` | deletes auth client assigned to auth code
`/consoles/[cliend_id]/agreements` | deletes reference to assigned agreement
