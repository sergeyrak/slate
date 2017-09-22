## Create Campaign Auth Code

> Example of campaign's auth code creation request:

```javascript
{
	type: 'create_campaign_auth_code',
	console_id: '-Bjasf8234l',
	bundle: {
		campaign_id: '-Kha84laiFaj'
	}
}
```

Creates a new auth code for existing console's campaign.

**Request parameters**

Parameter  | Required | Description
-----------|----------|------------
type | YES | `'create_campaign_auth_code'`
bundle.campaign_id | YES | campaign ID

> Example of response for creation campaign's auth code:

```javascript
{
	request_id: '-HU48fja9Hd',
	auth_code: '5ae5bf46-2a47-477d-973e-a5dacda42f1c'
}
```

**Response parameters**

Parameter  | Description
-----------|------------
auth_code | created auth code

> Example of modified endpoints after processed campaign's auth code creation request:

```javascript
campaigns: {
	'-Kha84laiFaj': {
		auth_codes: {
			'5ae5bf46-2a47-477d-973e-a5dacda42f1c': {
				active: true
			}
		}
	}
}
```

**Modified endpoints**

Endpoint  | Description
-----------|------------
`/campaigns/[campaign_id]/auth_codes` | adds a new auth code to campaign instance
