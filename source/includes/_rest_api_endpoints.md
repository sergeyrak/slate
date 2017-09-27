# REST API Endpoints

URL format: 

## API Key Verification

curl "http://https://ip-gifty-console-staging.herokuapp.com/api/verify?key=5a6b5f3f-5845-459c-9c97-89f34ca021e2"

{"status": "success"}

HTTP/1.1 400 Bad Request

curl "http://ip-gifty-console-staging.herokuapp.com/api?key=5a6b5f3f-5845-459c-9c97-89f34ca021e2&type=get_offers"

[{
	"id": "gravity_yyc_cappuccino",
	"name": "Gravity YYC Cappuccino"
}, {
	"id": "gravity_yyc_chardonnay",
	"name": "Gravity YYC Chardonnay"
},{
	"id": "gravity_yyc_cider",
	"name": "Gravity YYC Cider"
},{
	"id": "gravity_yyc_latte",
	"name": "Gravity YYC Latte"
},{
	"id": "gravity_yyc_rose",
	"name": "Gravity YYC Rose"
},{
	"id": "ollia_offer_tea",
	"name": "Ollia Offer Tea"
},{
	"id": "ollia_offer_three",
	"name": "Ollia Offer Three"
}]

HTTP/1.1 400 Bad Request

curl "http://ip-gifty-console-staging.herokuapp.com/api?key=5a6b5f3f-5845-459c-9c97-89f34ca021e2&type=link_create&offer=gravity_yyc_chardonnay"

{
 	"request_id": "-Kux_EhzastWPiNM8fLy",
	"link": "SJmMfjwiZ",
	"uri": "https://gifty.link/SJmMfjwiZ"
}

HTTP/1.1 400 Bad Request
