## Add Campaign User

> Example of request for adding user (phone) to campaign:

```javascript
{
	type: 'add_campaign_user',
	console_id: '-Bjasf8234l',
	bundle: {
		campaign_id: '-Kha84laiFaj',
		auth_code: 'beb0eee9-9ece-4422-a423-bb8f3bc5ba7c',
		user_id: '+111222333444',
		user_type: 'phone'
	}
}
```

Adds a new user to console's campaign. User can be email address or phone number.
Phone numbers require a free auth code to be provided.
If user is already assigned to another campaign, his access to that campaign is revoked and he will be accosiated with new one.

**Request parameters**

Parameter  | Required | Description
-----------|----------|------------
type | YES | `'add_campaign_user'`
bundle.campaign_id | YES | campaign ID
bundle.auth_code | YES | auth code which is required only for `'phone'` user
bundle.user_id | YES | phone number or email address
bundle.user_type | YES | user's type: `'email'` or `'phone'`

> Example of successfull response after adding a phone to campaign:

```javascript
{
	request_id: '-Ykjha7834ja',
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
		auth_codes: {
			'beb0eee9-9ece-4422-a423-bb8f3bc5ba7c': {
				active: true,
				user: '+111222333444'
			}
		},
		phones: {
			'+111222333444': {
				code: 'beb0eee9-9ece-4422-a423-bb8f3bc5ba7c',
				active: true
			}
		}
	}
},
consoles_users: {
	'+111222333444': {
		type: 'phone',
		consoles: {
			'-Bjasf8234l': {
				campaigns: {
					'-Kha84laiFaj': 'beb0eee9-9ece-4422-a423-bb8f3bc5ba7c'
				}
			}
		}
	}
}
```

**Modified endpoints**

Endpoint  | Description
-----------|------------
`/campaigns/[campaign_id]/[user_type]` | creates a reference to user
`/campaigns/auth_codes/[code]` | adds a reference to user for used auth code
`/consoles_users/[user_id]` | adds a new user information
