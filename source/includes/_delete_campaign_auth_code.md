## Delete Campaign Auth Code

> Example of request for deleting campaign's auth code:

```javascript
{
	type: 'delete_campaign_auth_code',
	console_id: '-Bjasf8234l',
	bundle: {
		campaign_id: '-Kha84laiFaj',
		auth_code: '5ae5bf46-2a47-477d-973e-a5dacda42f1c'
	}
}
```

Deletes an existing campaign's auth code. If auth code is associated with user, it will be removed from campaign as well.

**Request parameters**

Parameter  | Required | Description
-----------|----------|------------
type | YES | `'delete_campaign_auth_code'`
bundle.campaign_id | YES | campaign ID
bundle.auth_code | YES | auth code

> Example of response after deleting campaigns's auth code:

```javascript
{
	request_id: '-N8padslq03',
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
`/campaigns/[campaign_id]/auth_codes` | deletes auth code from campaign instance
