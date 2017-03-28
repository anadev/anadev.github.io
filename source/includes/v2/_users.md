# [V2] User

## Update User Information

```shell
curl -X PUT
     -H "X-User-Email: warex03@gmail.com"
     -H "X-User-Token: _KHS4euMs1At4jsUHHdR"
     -F "name=Arvin Dino"
     -F "contact_number=09271234567"
     -F "password=newpass"
     -F "current_password=oldpass"
https://try.payswitch.net/api/v2/users/<id>
```

```ruby
require 'net/https'

uri = URI("https://try.payswitch.net/api/v2/users/<id>")
params = {
  name: "Arvin Dino",
  contact_number: "09271234567",
  password: "newpass",
  current_password: "oldpass"
}
uri.query = URI.encode_www_form(params)

http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE
request_uri = Net::HTTP::Put.new(uri.request_uri)
request_uri.add_field("X-User-Email", "warex03@gmail.com")
request_uri.add_field("X-User-Token", "_KHS4euMs1At4jsUHHdR")

response = http.request(request_uri)
body = response.body
```

```python
import urllib, httplib

URL = "www.payswitch.net"
URI = "/api/v2/users/<id>"
HEADERS = {
    "Content-type": "application/x-www-form-urlencoded",
    "X-User-Email" : "warex03@gmail.com",
    "X-User-Token" : "_KHS4euMs1At4jsUHHdR"
}
DATA = {
  "name" : "Arvin Dino",
  "contact_number" : "09271234567",
  "password" : "newpass",
  "current_password" : "oldpass"
}

params = urllib.urlencode(DATA)
conn = httplib.HTTPSConnection(URL)
conn.request("PUT", URI, params, HEADERS)
response = conn.getresponse()
data = response.read()
```
> JSON output

```json
{
    "success": true,
    "info": {
        "id": 1,
        "email": "warex03@gmail.com",
        "name": "Arvin Dino",
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

### HTTPS Request

`PUT https://try.payswitch.net/api/v2/users/<id>`

### Payload

Parameter        | Type                   | Description
---------------- | ---------------------- | ---------------------------
name             | string<br />(optional) | The user's name
contact_number   | string<br />(optional) | The user's contact number
current_password | string<br />(required) | The user's current password
password         | string<br />(optional) | The user's new password

### Header Parameters

Parameter | Type | Description
--------- | ------- | -----------
Content-type | string<br />(optional) | For some libraries that url encodes the payload, specify the value as 'application/x-www-form-urlencoded'
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token