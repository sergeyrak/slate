## Set Campaign Offer

> Example of request to set a default campaign's offer:

```javascript
{
	type: 'set_campaign_offer',
	console_id: '-Bjasf8234l',
	bundle: {
		campaign_id: '-Kha84laiFaj',
		offer: 'ollia_offer_tea'
	}
}
```

Sets a default campaign's offer.

**Request parameters**

Parameter  | Required | Description
-----------|----------|------------
type | YES | `'set_campaign_offer'`
bundle.campaign_id | YES | campaign ID
bundle.offer | YES | offer ID

> Example of response after campaign's offer has been set:

```javascript
{
	request_id: '-Y7Jla4a90U',
	status: 'success'
}
```

**Response parameters**

Parameter  | Description
-----------|------------
status | operation status: if it was successfull - `'success'`, otherwise  - `'failure'`

> Example of modified endpoints after processed request:

```javascript
campaigns: {
	'-Kha84laiFaj': {
		offer: {
			id: 'ollia_offer_tea',
			vendor: 'ollia'
		}
	}
}
```

**Modified endpoints**

Endpoint  | Description
-----------|------------
`/campaigns/[campaign_id]/offer` | sets campaign's default offer details
