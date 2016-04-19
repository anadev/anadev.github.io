# Products


## Get All Products

```shell
curl -X GET
     -H 'X-User-Email: warex03@gmail.com'
     -H 'X-User-Token: _KHS4euMs1At4jsUHHdR'
http://www.payswitch.net/api/products
```

```ruby
require 'net/https'

URL = "http://www.payswitch.net/api/products"

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

URL = "http://www.payswitch.net/api/products"
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
    "product_category_id": 4,
    "name": "Sun 10"
  },
  {
    "id": 2,
    "product_category_id": 4,
    "name": "Sun 50"
  },
  {
    "id": 3,
    "product_category_id": 4,
    "name": "Sun 150"
  },
  {
    "id": 4,
    "product_category_id": 4,
    "name": "Sun 300"
  },
  {
    "id": 5,
    "product_category_id": 4,
    "name": "Sun 500"
  }
]
```

Get the list of all products.

### HTTP Request

`GET http://www.payswitch.net/api/products`

### Header Parameters

Parameter | Type | Description
--------- | ------- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token


## Get Product Details

```shell
curl -X GET
     -H 'X-User-Email: warex03@gmail.com'
     -H 'X-User-Token: _KHS4euMs1At4jsUHHdR'
http://www.payswitch.net/api/products/<id>
```

```ruby
require 'net/https'

URL = "http://www.payswitch.net/api/products/<id>"

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

URL = "http://www.payswitch.net/api/products/<id>"
HEADERS = {
    'X-User-Email' : 'warex03@gmail.com',
    'X-User-Token' : '_KHS4euMs1At4jsUHHdR'
}

response = requests.get(URL, headers=HEADERS)
```

> The JSON return value looks like this:

```json
{
  "id": 55,
  "product_category_id": 2,
  "sku": "GLOBEUnlitxt20",
  "name": "Globe Unlitxt20",
  "credits": "20.0",
  "enabled": false,
  "created_at": "2014-09-10T13:33:01.000+08:00",
  "description": "Globe Promos",
  "payload": {
    "account_id": "string"
  }
}
```

> The JSON return value when you try to fetch a non-existing product

```json
[
  {
    "Error": "Couldn't find Product with id=500"
  }
]
```

Get the details of a product given its id.

### HTTP Request

`GET http://www.payswitch.net/api/products/<id>`

### Header Parameters

Parameter | Type | Description
--------- | ------- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token

## Get Top Products

```shell
curl -X GET
     -H 'X-User-Email: warex03@gmail.com'
     -H 'X-User-Token: _KHS4euMs1At4jsUHHdR'
http://www.payswitch.net/api/products/top
```

```ruby
require 'net/https'

uri = URI("http://www.payswitch.net/api/products/top")

http = Net::HTTP.new(uri.host, uri.port)
request_uri = Net::HTTP::Get.new(uri.request_uri)
request_uri.add_field('X-User-Email', 'warex03@gmail.com')
request_uri.add_field('X-User-Token', '_KHS4euMs1At4jsUHHdR')

response = http.request(request_uri)
body = response.body
```

```python
import requests

URL = "http://www.payswitch.net/api/products/top"
HEADERS = {
    'X-User-Email' : 'warex03@gmail.com',
    'X-User-Token' : '_KHS4euMs1At4jsUHHdR'
}

response = requests.get(URL, headers=HEADERS)
```

> JSON output

```json
[
    {
        "id": 351,
        "name": "Globe 30",
        "product_category": {
            "id": 2,
            "name": "Globe",
            "created_at": "2014-09-10T13:32:56.000+08:00"
        },
        "product_type": 1
    },
    {
        "id": 95,
        "name": "Smart All Calls 100",
        "product_category": {
            "id": 3,
            "name": "Smart",
            "created_at": "2014-09-10T13:32:56.000+08:00"
        },
        "product_type": 1
    },
    {
        "id": 218,
        "name": "PLDT",
        "product_category": {
            "id": 18,
            "name": "Telecom",
            "created_at": "2014-09-10T13:32:56.000+08:00"
        },
        "product_type": 15
    },
    {
        "id": 184,
        "name": "MERALCO",
        "product_category": {
            "id": 16,
            "name": "Power & Water",
            "created_at": "2014-09-10T13:32:56.000+08:00"
        },
        "product_type": 15
    },
    {
        "id": 136,
        "name": "Garena 10 points",
        "product_category": {
            "id": 7,
            "name": "GArena",
            "created_at": "2014-09-10T13:32:56.000+08:00"
        },
        "product_type": 5
    },
    {
        "id": 122,
        "name": "GCash Cash-in",
        "product_category": {
            "id": 13,
            "name": "GCash",
            "created_at": "2014-09-10T13:32:56.000+08:00"
        },
        "product_type": 12
    },
    {
        "id": 47,
        "name": "Globe 200",
        "product_category": {
            "id": 2,
            "name": "Globe",
            "created_at": "2014-09-10T13:32:56.000+08:00"
        },
        "product_type": 1
    }
]
```

Get top 10 products of the day.

### HTTP Request

`GET http://www.payswitch.net/api/products/top`

### Header Parameters

Parameter | Type | Description
--------- | ------- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token

## Get Top Eloads

```shell
curl -X GET
     -H 'X-User-Email: warex03@gmail.com'
     -H 'X-User-Token: _KHS4euMs1At4jsUHHdR'
     -F "type=eloads"
http://www.payswitch.net/api/products/top
```

```ruby
require 'net/https'

uri = URI("http://www.payswitch.net/api/products/top")
params = {
  type: 'eloads'
}
uri.query = URI.encode_www_form(params)

http = Net::HTTP.new(uri.host, uri.port)
request_uri = Net::HTTP::Get.new(uri.request_uri)
request_uri.add_field('X-User-Email', 'warex03@gmail.com')
request_uri.add_field('X-User-Token', '_KHS4euMs1At4jsUHHdR')

response = http.request(request_uri)
body = response.body
```

```python
import requests

URL = "http://www.payswitch.net/api/products/top"
HEADERS = {
    'X-User-Email' : 'warex03@gmail.com',
    'X-User-Token' : '_KHS4euMs1At4jsUHHdR'
}
PARAMS = {
  'type': 'eloads'
}

response = requests.get(URL, headers=HEADERS, data=PARAMS)
```

> JSON output

```json
[
    {
        "id": 336,
        "name": "Globe 15",
        "product_category": {
            "id": 2,
            "name": "Globe",
            "created_at": "2014-09-10T13:32:56.000+08:00"
        },
        "product_type": 1
    },
    {
        "id": 351,
        "name": "Globe 30",
        "product_category": {
            "id": 2,
            "name": "Globe",
            "created_at": "2014-09-10T13:32:56.000+08:00"
        },
        "product_type": 1
    },
    {
        "id": 361,
        "name": "Globe 40",
        "product_category": {
            "id": 2,
            "name": "Globe",
            "created_at": "2014-09-10T13:32:56.000+08:00"
        },
        "product_type": 1
    },
    {
        "id": 18,
        "name": "Sun Call & Text Combo 20",
        "product_category": {
            "id": 4,
            "name": "Sun",
            "created_at": "2014-09-10T13:32:56.000+08:00"
        },
        "product_type": 1
    },
    {
        "id": 47,
        "name": "Globe 200",
        "product_category": {
            "id": 2,
            "name": "Globe",
            "created_at": "2014-09-10T13:32:56.000+08:00"
        },
        "product_type": 1
    },
    {
        "id": 356,
        "name": "Globe 35",
        "product_category": {
            "id": 2,
            "name": "Globe",
            "created_at": "2014-09-10T13:32:56.000+08:00"
        },
        "product_type": 1
    },
    {
        "id": 381,
        "name": "Globe 60",
        "product_category": {
            "id": 2,
            "name": "Globe",
            "created_at": "2014-09-10T13:32:56.000+08:00"
        },
        "product_type": 1
    },
    {
        "id": 95,
        "name": "Smart All Calls 100",
        "product_category": {
            "id": 3,
            "name": "Smart",
            "created_at": "2014-09-10T13:32:56.000+08:00"
        },
        "product_type": 1
    },
    {
        "id": 114,
        "name": "Smart 60",
        "product_category": {
            "id": 3,
            "name": "Smart",
            "created_at": "2014-09-10T13:32:56.000+08:00"
        },
        "product_type": 1
    },
    {
        "id": 116,
        "name": "Smart 115",
        "product_category": {
            "id": 3,
            "name": "Smart",
            "created_at": "2014-09-10T13:32:56.000+08:00"
        },
        "product_type": 1
    }
]
```

Get top 10 eload products of the month.

### HTTP Request

`GET http://www.payswitch.net/api/products/top`

### Header Parameters

Parameter | Type | Description
--------- | ------- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token

### Query Parameters

Paramter | Type | Description
-------- | ---- | -----------
type | string<br />(required) | The type of product

## Get Top Billers

```shell
curl -X GET
     -H 'X-User-Email: warex03@gmail.com'
     -H 'X-User-Token: _KHS4euMs1At4jsUHHdR'
     -F "type=billers"
http://www.payswitch.net/api/products/top
```

```ruby
require 'net/https'

uri = URI("http://www.payswitch.net/api/products/top")
params = {
  type: 'billers'
}
uri.query = URI.encode_www_form(params)

http = Net::HTTP.new(uri.host, uri.port)
request_uri = Net::HTTP::Get.new(uri.request_uri)
request_uri.add_field('X-User-Email', 'warex03@gmail.com')
request_uri.add_field('X-User-Token', '_KHS4euMs1At4jsUHHdR')

response = http.request(request_uri)
body = response.body
```

```python
import requests

URL = "http://www.payswitch.net/api/products/top"
HEADERS = {
    'X-User-Email' : 'warex03@gmail.com',
    'X-User-Token' : '_KHS4euMs1At4jsUHHdR'
}
PARAMS = {
  'type': 'billers'
}

response = requests.get(URL, headers=HEADERS, data=PARAMS)
```

> JSON output

```json
[
    {
        "id": 184,
        "name": "MERALCO",
        "product_category": {
            "id": 16,
            "name": "Power & Water",
            "created_at": "2014-09-10T13:32:56.000+08:00"
        },
        "product_type": 15
    },
    {
        "id": 197,
        "name": "NSO - Helpline Plus",
        "product_category": {
            "id": 17,
            "name": "Government Services",
            "created_at": "2014-09-10T13:32:56.000+08:00"
        },
        "product_type": 15
    },
    {
        "id": 214,
        "name": "Globe Postpaid Plans",
        "product_category": {
            "id": 18,
            "name": "Telecom",
            "created_at": "2014-09-10T13:32:56.000+08:00"
        },
        "product_type": 15
    },
    {
        "id": 218,
        "name": "PLDT",
        "product_category": {
            "id": 18,
            "name": "Telecom",
            "created_at": "2014-09-10T13:32:56.000+08:00"
        },
        "product_type": 15
    },
    {
        "id": 312,
        "name": "BDO Credit Card",
        "product_category": {
            "id": 26,
            "name": "Banks",
            "created_at": "2014-09-10T13:32:56.000+08:00"
        },
        "product_type": 15
    }
]
```

Get top 10 billers of the month.

### HTTP Request

`GET http://www.payswitch.net/api/products/top`

### Header Parameters

Parameter | Type | Description
--------- | ------- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token

### Query Parameters

Paramter | Type | Description
-------- | ---- | -----------
type | string<br />(required) | The type of product
