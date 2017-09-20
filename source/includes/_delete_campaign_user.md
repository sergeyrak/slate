## Delete Campaign User

> Example of request for deleting user from campaign:

```javascript
{
	type: 'delete_campaign_user',
	console_id: '-Bjasf8234l',
	bundle: {
		campaign_id: '-Kha84laiFaj',
		user_id: '+111222333444'
	}
}
```

Deletes an existing user from console's campaign.

**Request parameters**

Parameter  | Required | Description
-----------|----------|------------
type | YES | `'delete_campaign_user'`
bundle.campaign_id | YES | campaign ID
bundle.user_id | YES | phone number or email address

> Example of successfull response after deleting a user from campaign:

```javascript
{
	request_id: '-KW7k2bm292as',
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
`/campaigns/[campaign_id]/[user_type]` | deletes a user reference from campaign
`/campaigns/auth_codes/[code]` | frees associated auth code in case of phone number
`/consoles_users/[user_id]` | deletes user instance
