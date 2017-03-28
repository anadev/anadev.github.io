# Receipts

## Send Receipt via SMS

```shell
curl -X	POST
	 -F 'type=sms'
	 -F 'recipient=09273031099'
https://try.payswitch.net/api/receipts/<id>
```

```ruby
require 'net/https'

uri = URI('https://try.payswitch.net/api/receipts/<id>')
params = {
	"type" => "sms",
	"recipient" => "09273031099"
}
http = Net::HTTP.new(uri.host, uri.port)
request_uri = Net::HTTP::Post.new(uri.request_uri)
request_uri.set_form_data(params)

response = http.request(request_uri)
body = response.body
```

```python
import requests

URL = "https://try.payswitch.net/api/receipts/<id>"
PARAMS = {
	"type" : "sms",
	"recipient" : "09273031099"
}

response = requests.post(URL, data=PARAMS)
```

> The JSON return value looks like this:

```json
{
  "message": "success"
}
```

> The JSON return value when you try to get a receipt for a non-existent transaction

```json
{
  "success": false,
  "message": "Couldn't find transaction with id=500"
}
```

Send a copy of the receipt of a specific transaction with the provided transaction id via SMS.

### Query Parameters

Parameter | Type | Description
--------- | ---- | -----------
type | string<br/>(optional) | Method of sending receipt. (email or sms)
recipient | string<br/>(optional) | Mobile number where the receipt will be sent.

## Send Receipt via E-mail

```shell
curl -X	POST
	 -F 'type=email'
	 -F 'recipient=warex03@gmail.com'
https://try.payswitch.net/api/receipts/<id>
```

```ruby
require 'net/https'

uri = URI('https://try.payswitch.net/api/receipts/<id>')
params = {
	"type" => "email",
	"recipient" => "warex03@gmail.com"
}
http = Net::HTTP.new(uri.host, uri.port)
request_uri = Net::HTTP::Post.new(uri.request_uri)
request_uri.set_form_data(params)

response = http.request(request_uri)
body = response.body
```

```python
import requests

URL = "https://try.payswitch.net/api/receipts/<id>"
PARAMS = {
	"type" : "email",
	"recipient" : "benjamin.cueto@payswitch.net"
}
response = requests.post(URL, data=PARAMS)
```

> The JSON return value looks like this:

```json
{
  "message": "success"
}
```

> The JSON return value when you try to get a receipt for a non-existent transaction

```json
{
  "success": false,
  "message": "Couldn't find transaction with id=500"
}
```

Send a copy of the receipt of a specific transaction with the provided transaction id via e-mail.

### Query Parameters

Parameter | Type | Description
--------- | ---- | -----------
type | string<br/>(optional) | Method of sending receipt. (email or sms)
recipient | string<br/>(optional) | E-mail address where the receipt will be sent.


> The JSON return value looks like this if the 'type' field is left empty:

```json
{
  "id": 39639,
  "payload": {
    "account_id": "09473616056"
  },
  "cost": "10.0",
  "created_at": "2015-07-13T15:37:25.000+08:00",
  "provider_refno": "082109486493",
  "provider_message": {
    "code": "2",
    "message": "Request successfully processes."
  },
  "transaction_status": {
    "code": "00",
    "name": "Successful",
    "description": "Transaction has been successful"
  },
  "user": {
    "id": 71,
    "type": "Branch",
    "name": "New Batong Malake Public Market MPC",
    "merchant": {
      "id": 35,
      "name": "Direct Agent 5"
    }
  },
  "provider_product": {
    "id": 96,
    "product_category_root_id": 1,
    "product": {
      "id": 96,
      "name": "Smart All Text 10"
    },
    "provider": {
      "id": 1,
      "name": "OksPinoy"
    }
  }
}
```
