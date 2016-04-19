# Merchant

## Get All Branches of merchant

```shell
curl -X GET
     -H 'X-User-Email: warex03@gmail.com'
     -H 'X-User-Token: _KHS4euMs1At4jsUHHdR'
http://www.payswitch.net/api/merchants/branches
```

```ruby
require 'net/https'

uri = URI("http://www.payswitch.net/api/merchants/branches")

http = Net::HTTP.new(uri.host, uri.port)
request_uri = Net::HTTP::Get.new(uri.request_uri)
request_uri.add_field('X-User-Email', 'warex03@gmail.com')
request_uri.add_field('X-User-Token', '_KHS4euMs1At4jsUHHdR')

response = http.request(request_uri)
body = response.body
```

```python
import requests

URL = "http://www.payswitch.net/api/merchants/branches"
HEADERS = {
    'X-User-Email' : 'warex03@gmail.com',
    'X-User-Token' : '_KHS4euMs1At4jsUHHdR'
}

response = requests.get(URL, headers=HEADERS)
```
> JSON output

```json
{
    "id": 1,
    "name": "Demo Merchant",
    "branches": [
        {
            "id": 2,
            "email": "branch@demomerchant.com",
            "merchant_id": 1,
            "name": "Demo Branch",
            "contact_number": "09273031099",
            "banned": false,
            "balance": "19.0"
        },
        {
            "id": 51,
            "email": "sample_branch@demomerchant.com",
            "merchant_id": 1,
            "name": "Sample Branch",
            "contact_number": "09113356989",
            "banned": false,
            "balance": "0.0"
        }
    ]
}
```
Get the details of the current user

### HTTP Request

`GET http://www.payswitch.net/api/merchants/branches`

### Header Parameters

Parameter | Type | Description
--------- | ------- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token

### PERMISSIONS

User Type | Has access | Description
--------- | ---------- | -----------
Merchant | TRUE | Return list of Branches.
Branch | FALSE | Permission error message.
Agent | FALSE | Permission error message.
