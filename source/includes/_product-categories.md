# Product Categories


## Get Main Product Categories

```shell
curl -X GET
     -H 'X-User-Email: warex03@gmail.com'
     -H 'X-User-Token: _KHS4euMs1At4jsUHHdR'
http://www.payswitch.net/api/product_categories/main
```

```ruby
require 'net/https'

URL = "http://www.payswitch.net/api/product_categories/main"

uri = URI.parse(URL)
http = Net::HTTP.new(uri.host, uri.port)
request_uri = Net::HTTP::Get.new(uri.request_uri)
request_uri.add_field('X-User-Email', 'warex03@gmail.com')
request_uri.add_field('X-User-Token', '_KHS4euMs1At4jsUHHdR')
response = http.request(request_uri)
body = response.body
```

```python
import requests

URL = "http://www.payswitch.net/api/product_categories/main"
HEADERS = {
    'X-User-Email' : 'warex03@gmail.com',
    'X-User-Token' : '_KHS4euMs1At4jsUHHdR'
}

response = requests.get(URL, headers=HEADERS)
```

> The JSON return value looks like this:

```json
[
    {
        "id": 1,
        "name": "E-load",
        "created_at": "2014-09-10T13:32:56.000+08:00"
    },
    {
        "id": 5,
        "name": "Gaming Pins",
        "created_at": "2014-09-10T13:32:56.000+08:00"
    },
    {
        "id": 12,
        "name": "Mobile Money",
        "created_at": "2014-09-10T13:32:56.000+08:00"
    },
    {
        "id": 15,
        "name": "Bills Payment",
        "created_at": "2014-09-10T13:32:56.000+08:00"
    },
    {
        "id": 28,
        "name": "Travel",
        "created_at": "2014-09-10T13:32:56.000+08:00"
    },
    {
        "id": 29,
        "name": "Microinsurance",
        "created_at": "2014-09-10T13:32:56.000+08:00"
    }
]
```

Get the main product categories.

### HTTP Request

### V1
`GET http://www.payswitch.net/api/product_categories/main`

### V2
`GET https://www.payswitch.net/api/v2/product_categories/main`

### Header Parameters

Parameter | Type | Description
--------- | ------- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token


## Get Product Categories with Product Listing

```shell
curl -X GET
     -H 'X-User-Email: warex03@gmail.com'
     -H 'X-User-Token: _KHS4euMs1At4jsUHHdR'
http://www.payswitch.net/api/product_categories/<id>
```

```ruby
require 'net/https'

URL = "http://www.payswitch.net/api/product_categories/<id>"

uri = URI.parse(URL)
http = Net::HTTP.new(uri.host, uri.port)
request_uri = Net::HTTP::Get.new(uri.request_uri)
request_uri.add_field('X-User-Email', 'warex03@gmail.com')
request_uri.add_field('X-User-Token', '_KHS4euMs1At4jsUHHdR')
response = http.request(request_uri)
body = response.body
```

```python
import requests

URL = "http://www.payswitch.net/api/product_categories/<id>"
HEADERS = {
    'X-User-Email' : 'warex03@gmail.com',
    'X-User-Token' : '_KHS4euMs1At4jsUHHdR'
}

response = requests.get(URL, headers=HEADERS)
```

> The JSON return value looks like this:

```json
{
  "id": 6,
  "name": "E-Games",
  "description": null,
  "position": null,
  "products": [
    {
      "id": 127,
      "name": "E-games 10 points",
      "description": "E-games 10 points",
      "payload": {
        "account_id": "string"
      }
    },
    {
      "id": 128,
      "name": "E-games 100 points",
      "description": "E-games 100 points",
      "payload": {
        "account_id": "string"
      }
    },
    {
      "id": 129,
      "name": "E-games 1000 points",
      "description": "E-games 1000 points",
      "payload": {
        "account_id": "string"
      }
    }
  ],
  "children": []
}
```

Get the product categories containing the list of their products (if available).

### HTTP Request

### V1
`GET http://www.payswitch.net/api/product_categories/<id>`

### V2
`GET https://www.payswitch.net/api/v2/product_categories/<id>`

### Header Parameters

Parameter | Type | Description
--------- | ------- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token
