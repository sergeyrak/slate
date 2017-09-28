# REST API Endpoints

## Verify Key

> Example:

```javascript
curl "http://https://gifty.link/api/verify?key=5a6b5f3f-5845-459c-9c97-89f34ca021e3"
```

> Response: 

```javascript
{
	'status': 'success'
}
```

URL: `/api/verify?key=[api_key]`

Returns `HTTP 200 OK` and JSON payload `{"status: "success"}` if key's verification is successfull, otherwise - `HTTP 400 Bad Request`.

## Get Available Offers

> Example:

```javascript
curl "http://gifty.link/api?key=5a6b5f3f-5845-459c-9c97-89f34ca021e3&type=get_offers"
```

> Response:

```javascript
[{
	'id': 'gravity_yyc_cappuccino',
	'name': 'Gravity YYC Cappuccino'
}, {
	'id': 'gravity_yyc_chardonnay',
	'name': 'Gravity YYC Chardonnay'
},{
	'id': 'ollia_offer_tea',
	'name': 'Ollia Offer Tea'
},{
	'id': 'ollia_offer_three',
	'name': 'Ollia Offer Three'
}]
```

URL: `/api/?key=[api_key]&type=get_offers`

Returns `HTTP 200 OK` and array of available offers IDs and name in JSON format if request is successfull, otherwise - `HTTP 400 Bad Request`.

## Link Creation

> Example:

```javascript
curl "http://gifty.link/api?key=5a6b5f3f-5845-459c-9c97-89f34ca021e3&type=create_link&offer=gravity_yyc_chardonnay"
```

> Response:

```javascript
{
 	'request_id': '-Kux_EhzastWPiNM8fLy',
	'link': 'SJmMfjwiZ',
	'uri': 'https://gifty.link/SJmMfjwiZ'
}
```

URL: `/api/?key=[api_key]&type=create_link&offer=[offer_id]`

Returns `HTTP 200 OK` and created link details in JSON format if request is successfull, otherwise - `HTTP 400 Bad Request`.

