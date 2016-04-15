# User

## Get Current User Details

```shell
curl -X GET
     -H 'X-User-Email: warex03@gmail.com'
     -H 'X-User-Token: _KHS4euMs1At4jsUHHdR'
http://www.payswitch.net/api/users/current
```

```ruby
require 'net/https'

uri = URI("http://www.payswitch.net/api/users/current")

http = Net::HTTP.new(uri.host, uri.port)
request_uri = Net::HTTP::Get.new(uri.request_uri)
request_uri.add_field('X-User-Email', 'warex03@gmail.com')
request_uri.add_field('X-User-Token', '_KHS4euMs1At4jsUHHdR')

response = http.request(request_uri)
body = response.body
```

```python
import requests

URL = "https://www.payswitch.net/api/users/current"
HEADERS = {
    'X-User-Email' : 'warex03@gmail.com',
    'X-User-Token' : '_KHS4euMs1At4jsUHHdR'
}

response = requests.get(URL, headers=HEADERS)
```
> JSON output

```json
{
    "success": true,
    "info": {
        "id": 1,
        "email": "admin@demomerchant.com",
        "name": "Demo Merchant",
        "authentication_token": "gdzhhNsa7uVkxrzXsy4_",
        "contact_number": "",
        "banned": false
    },
    "user_type": "Merchant",
    "merchant_plan": null,
    "balance": "399.00"
}
```
Get the details of the current user

### HTTP Request

`GET http://www.payswitch.net/api/users/current`

### Header Parameters

Parameter | Type | Description
--------- | ------- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token
