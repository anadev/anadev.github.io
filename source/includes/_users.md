# User

## Get Current User Details

```shell
curl -X GET
     -H 'X-User-Email: warex03@gmail.com'
     -H 'X-User-Token: _KHS4euMs1At4jsUHHdR'
https://try.payswitch.net/api/users/current
```

```ruby
require 'net/https'

uri = URI("https://try.payswitch.net/api/users/current")

http = Net::HTTP.new(uri.host, uri.port)
request_uri = Net::HTTP::Get.new(uri.request_uri)
request_uri.add_field('X-User-Email', 'warex03@gmail.com')
request_uri.add_field('X-User-Token', '_KHS4euMs1At4jsUHHdR')

response = http.request(request_uri)
body = response.body
```

```python
import requests

URL = "https://try.payswitch.net/api/users/current"
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

`GET https://try.payswitch.net/api/users/current`

### Header Parameters

Parameter | Type | Description
--------- | ------- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token

## Update User Information

```shell
curl -X PUT
     -H "X-User-Email: warex03@gmail.com"
     -H "X-User-Token: _KHS4euMs1At4jsUHHdR"
     -F "name=Arvin Dinosaur"
     -F "contact_number=09271234567"
     -F "password=newpass"
     -F "current_password=oldpass"
https://try.payswitch.net/api/v2/users/<id>
```

```ruby
require 'net/https'

uri = URI("https://try.payswitch.net/api/v2/users/<id>")
params = {
  name: "Arvin Dinosaur",
  contact_number: "09271234567",
  password: "newpass",
  current_password: "oldpass"
}
uri.query = URI.encode_www_form(params)

http = Net::HTTP.new(uri.host, uri.port)
request_uri = Net::HTTP::Put.new(uri.request_uri)
request_uri.add_field("X-User-Email", "warex03@gmail.com")
request_uri.add_field("X-User-Token", "_KHS4euMs1At4jsUHHdR")

response = http.request(request_uri)
body = response.body
```

```python
import urllib
import urllib2

URL = "https://try.payswitch.net/api/v2/users/<id>"
HEADERS = {
    "X-User-Email" : "warex03@gmail.com",
    "X-User-Token" : "_KHS4euMs1At4jsUHHdR"
}
import urllib
import urllib2

OPENER = urllib2.build_opener(urllib2.HTTPHandler)
URL = "https://try.payswitch.net/api/v2/users/<id>"
HEADERS = {
    "X-User-Email" : "warex03@gmail.com",
    "X-User-Token" : "_KHS4euMs1At4jsUHHdR"
}

DATA = {
  "name" : "Arvin Dinosaur",
  "contact_number" : "09271234567",
  "password" : "newpass",
  "current_password" : "oldpass"
}

data = urllib.urlencode(DATA)
request = urllib2.Request(URL, data=data, headers=HEADERS)
request.get_method = lambda: 'PUT'
response = urllib2.urlopen(request).read()
```
> JSON output

```json
{
    "success": true,
    "info": {
        "id": 1,
        "email": "warex03@gmail.com",
        "name": "Arvin Dinosaur",
        "authentication_token": "_KHS4euMs1At4jsUHHdR",
        "contact_number": "09271234567",
        "banned": false
    },
    "user_type": "Merchant",
    "merchant_plan": null,
    "balance": "399.00"
}
```

Update the information of the current user

### HTTP Request

`PUT https://try.payswitch.net/api/v2/users/<id>`

### Payload

Parameter | Type | Description
--------- | ------- | -----------
name | string<br />(optional) | The user's name
contact_number | string<br />(optional) | The user's contact number
current_password | string<br />(required) | The user's current password
password | string<br />(required) | The user's new password

### Header Parameters

Parameter | Type | Description
--------- | ------- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token
