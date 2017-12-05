## Create Link

> Example of link creation request for user:

```javascript
{
	type: 'create_link',
	bundle: {
		user_id: '+111222333444',
		offer: 'ollia_offer_tea'
	}
}
```

> Example of link creation request for campaign:

```javascript
{
	type: 'create_link',
	bundle: {
		campaign_id: '-Kha84laiFaj',
		offer: 'ollia_offer_tea'
	}
}
```

> Example of MRGL link creation request:

```javascript
{
	type: 'create_link',
	bundle: {
		client_id: '+1234567890',
		offer: 'ollia_offer_tea',
		mrgl: {
			recipients_count: 3,
			ttl: 20
		}
	}
}
```

Creates a link for user or campaign.

Server searches for console related to provided user/campaign and tries to find the best agreement with offer's vendor to make a charge. 
If console's balance is lower than offer's price, first of all, console will be topped up.

**Request parameters**

Parameter  | Required | Description
-----------|----------|------------
type | YES | `'create_link'`
bundle.offer | YES | selected offer ID for link
bundle.user_id | NO | user ID who wants to create a link
bundle.campaign_id | NO | link must be created for campaign

**MRGL related parameters**
bundle.mrgl.recipients_count | YES | max recipients count
bundle.mrgl.ttl | YES | accept timeout in minutes

<aside class="notice">
Please notice that this request doesn't require a <b>console_id</b> attribute. That's why response is pushed directly to <b>responses path</b>/<b>request's wait_for_response_at</b>.
</aside>

> Example of link creation response:

```javascript
{
	request_id: '-JG28Kjale',
	link: 'SyywyKMj-',
	uri: 'http://gifty.link/SyywyKMj-'
}
```

**Response parameters**

Parameter  | Description
-----------|------------
link | created link ID
uri | created link URI


> Example of modified endpoints after processed console's API key creation request:

```javascript
consoles: {
	'-Bjasf8234l':
		links: {
			'SyywyKMj-': true
		}
	}
},
links: {
	'SyywyKMj-': {
		agreement: '-Kq2O90gCwo42qeQm16e_public',
		charge: {...},
		charge_record: '-KudVz0HBL1mSUOwZpMm',
		console: '-Bjasf8234l',
		discount: 0,
		kind: 'gift',
		limit: 1,
		offer_id: 'ollia_offer_tea',
		user: '+111222333444',
		vendor: 'ollia',
		timestamp: 1512506174707
	}
}
```

**Modified endpoints**

Endpoint  | Description
-----------|------------
`/consoles/[console_id]/links` | adds a reference to created link
`/links` | adds a link object with owner and charge details
`/transactions` | adds a charge record
`/pay` | adds a pay cheque

