## Create Agreement

> Example of agreement creation request:

```javascript
{
	type: 'create_agreement',
	console_id: '-Bjasf8234l',
	bundle: {
		name: 'My Agreement'
	}
}
```

Creates a new active agreement for console. 

Each console has a virtual *public agreement* to for users which don’t belong to any other console’s agreements. Public agreement has ID in  format: `[console_id]_public`.

**Request parameters**

Parameter  | Required | Description
-----------|----------|------------
type | YES | `'create_agreement'`
bundle.name | YES | agreement name

> Example of agreeement creation response:

```javascript
{
	request_id: '-HU48fja9Hd',
	agreement_id: '-KuYrIw65D3'
}
```

**Response parameters**

Parameter  | Description
-----------|------------
agreement_id | created agreement ID

> Example of modified endpoints after processed agreement creation request:

```javascript
agreements: {
	'-KuYrIw65D3': {
		name: 'My Agreement',
		console_id: '-Bjasf8234l',
	}
},
consoles: {
	'-Bjasf8234l': {
		agreements: {
			'-KuYrIw65D3': {
				active: true,
				owner: '-Bjasf8234l'
			}
		}
	}
}
```

**Modified endpoints**

Endpoint  | Description
-----------|------------
`/agreements` | adds a new agreement instance
`/consoles/[console_id]/agreements` | adds reference for created agreement
