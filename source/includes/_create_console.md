# API Endpoints

## Create Console

> Example of console creation request:

```javascript
{
	type: 'create_console',
	bundle: {
		name: 'My Console',
		vendor: 'rosso',
        uid: 'ajj234k091234ajlqrlerhj'
	}
}
```

Creates a new console and links it with registered user if user ID is provided.

**Request parameters**

Parameter  | Required | Description
-----------|----------|------------
type | YES | `'create_console'`
bundle.name | YES | console name
bundle.uid | YES | user ID which must be linked with new console
bundle.vendor | NO | vendor name

> Example of console creation response:

```javascript
{
	request_id: '-LJKd08jkad',
	console_id: '-Bjasf8234l'
}
```

**Response parameters**

Parameter  | Description
-----------|------------
console_id | created console ID

> Example of modified endpoints after processed console creation request:

```javascript
consoles: {
	'-Bjasf8234l': {
		name: 'My Console',
		console_id: '-Bjasf8234l',
		console_creation_date: 1505480785652,
		vendor: 'rosso',
		payment: {
			balance: {
				cad: {
					cents: 0
				}
			}
		}
	}
},
users: {
	'ajj234k091234ajlqrlerhj': '-Bjasf8234l'
},
consoles_by_vendor: {
	'rosso': '-Bjasf8234l'
}
```

**Modified endpoints**

Endpoint  | Description
-----------|------------
`/consoles` | adds a new console instance
`/users` | creates mapping for console by user ID
`/consoles_by_vendor` | creates mapping for console by vendor name if it was provided
