# Introduction

API is based on request-response pattern, in which:

* client sends request to server and is waiting for response.
* server receives request and sends response when request was processed.
* client receives a response.

## Request

> Example of create a new campaign request:

```javascript
{
	type: 'create_campaign',
	console_id: '-Hlk20dJKsd7',
	bundle: {
		name: 'My Campaign',
		type: 'email'
	}
}
```

Server accepts requests with next required parameters:

Parameter  | Description
-----------|--------------
type       | request type
console_id | originator console ID
bundle     | request related parameters
wait_for_response_at | path related to responses endpoint where server must push the response

## Response

> Example of response on create a new campaign request:

```javascript
{
	request_id: '-Lkjadf8134',
	campaign_id: '-B89daKsdf8'
}
```

> Full response's path in this case looks like <b>/api/v1/responses/-Hlk20dJKsd7</b>

Server responses have the next common parameters:

Parameter  | Description
-----------|--------------
request_id | original request ID
error | means the request processing has failed and contains error description

<aside class="notice">
Response's path is built like: <b>responses path</b>/<b>console_id</b>/<b>request's wait_for_response_at</b>, exception is the console creation request.
</aside>

## Endpoints

Path | Description
-----|-------------
`/api/v1/requests` | incomming requests endpoint
`/api/v1/responses` | outgoing responses endpoint
