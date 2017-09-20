## Create Campaign

> Example of campaign creation request:

```javascript
{
	type: 'create_campaign',
	console_id: '-Bjasf8234l',
	bundle: {
		name: 'My Campaign',
		type: 'email'
	}
}
```

Creates a new active campaign for console.

**Request parameters**

Parameter  | Required | Description
-----------|----------|------------
type | YES | `'create_campaign'`
bundle.name | YES | campaign name
bundle.type | YES | campaign type: `'email'` or `'phone'`

> Example of campaign creation response:

```javascript
{
	request_id: '-HU48fja9Hd',
	campaign_id: '-Kha84laiFaj'
}
```

**Response parameters**

Parameter  | Description
-----------|------------
campaign_id | created campaign ID

> Example of modified endpoints after processed campaign creation request:

```javascript
campaigns: {
	'-Kha84laiFaj': {
		name: 'My Campaign',
		type: 'email',
		console_id: '-Bjasf8234l',
	}
},
consoles: {
	'-Bjasf8234l': {
		campaigns: {
			'-Kha84laiFaj': {
				active: true
			}
		}
	}
}
```

**Modified endpoints**

Endpoint  | Description
-----------|------------
`/campaigns` | adds a new campaign instance
`/consoles/[console_id]/campaigns` | adds reference for created campaign
