# Transactions


## Get All Transactions

```shell
curl -X GET
     -H 'X-User-Email: warex03@gmail.com'
     -H 'X-User-Token: _KHS4euMs1At4jsUHHdR'
     -F "per_page=2"
     -F "page=1"
     -F "prod_cat_id=1"
     -F "date_from=2/2/2015"
     -F "date_to=4/2/2015"
     -F "branch_id=2"
     -F "agent_id=3"
http://www.payswitch.net/api/transactions
```

```ruby
require 'net/https'

uri = URI("http://www.payswitch.net/api/transactions")
params = {
  per_page: 2,
  page: 1,
  prod_cat_id: 1,
  date_from: '2/2/2015',
  date_to: '4/2/2015',
  branch_id: 2,
  agent_id: 3
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
import urllib2

URL = "http://www.payswitch.net/api/transactions"
HEADERS = {
    'X-User-Email' : 'warex03@gmail.com',
    'X-User-Token' : '_KHS4euMs1At4jsUHHdR'
}
PARAMS = {
    'per_page' : 2,
    'page' : 1,
    'prod_cat_id' : 1,
    'date_from' : '2/2/2015',
    'date_to' : '4/2/2015',
    'branch_id' : 2,
    'agent_id' : 3
}
QUERY_PARAMS = urllib.urlencode(PARAMS)
URL = URL + '?' + QUERY_PARAMS

request = urllib2.Request(URL, headers=HEADERS)
response = urllib2.urlopen(request).read()
```

> The JSON return value looks like this:

```json
{
    "total_items": 4,
    "transactions": [
        {
            "id": 1158,
            "payload": {
                "account_id": "09156426897"
            },
            "cost": "30.0",
            "created_at": "2015-02-04T14:34:39.000+08:00",
            "provider_refno": "1620638746",
            "provider_message": {
                "code": null,
                "message": "Transaction successful."
            },
            "transaction_status": {
                "code": "00",
                "name": "Successful",
                "description": "Transaction has been successful"
            },
            "user": {
                "id": 3,
                "type": "BranchAgent",
                "name": "Demo Agent",
                "merchant": {
                    "id": 1,
                    "name": "Demo Merchant"
                }
            },
            "provider_product": {
                "id": 337,
                "product_category_root_id": 1,
                "product": {
                    "id": 351,
                    "name": "Globe 30"
                },
                "provider": {
                    "id": 11,
                    "name": "EcpayLoad"
                }
            }
        },
        {
            "id": 1157,
            "payload": {
                "account_id": "09273031099"
            },
            "cost": "15.0",
            "created_at": "2015-02-04T13:39:30.000+08:00",
            "provider_refno": "09273031099150204134004",
            "provider_message": {
                "code": null,
                "message": "Transaction successful."
            },
            "transaction_status": {
                "code": "00",
                "name": "Successful",
                "description": "Transaction has been successful"
            },
            "user": {
                "id": 3,
                "type": "BranchAgent",
                "name": "Demo Agent",
                "merchant": {
                    "id": 1,
                    "name": "Demo Merchant"
                }
            },
            "provider_product": {
                "id": 502,
                "product_category_root_id": 1,
                "product": {
                    "id": 336,
                    "name": "Globe 15"
                },
                "provider": {
                    "id": 3,
                    "name": "Ayannah"
                }
            }
        },
        {
            "id": 1149,
            "payload": {
                "account_id": "09232979579"
            },
            "cost": "50.0",
            "created_at": "2015-02-02T14:54:51.000+08:00",
            "provider_refno": "OTH-vyl2k4450aqzwm45cwau0055",
            "provider_message": {
                "code": null,
                "message": "Transaction successful."
            },
            "transaction_status": {
                "code": "00",
                "name": "Successful",
                "description": "Transaction has been successful"
            },
            "user": {
                "id": 3,
                "type": "BranchAgent",
                "name": "Demo Agent",
                "merchant": {
                    "id": 1,
                    "name": "Demo Merchant"
                }
            },
            "provider_product": {
                "id": 20,
                "product_category_root_id": 1,
                "product": {
                    "id": 20,
                    "name": "Sun Call & Text Combo 50"
                },
                "provider": {
                    "id": 2,
                    "name": "Xpressload"
                }
            }
        },
        {
            "id": 1148,
            "payload": {
                "account_id": "09331994071"
            },
            "cost": "50.0",
            "created_at": "2015-02-02T14:52:39.000+08:00",
            "provider_refno": "OTH-x0ti5fn5vhivt2455yrejq55",
            "provider_message": {
                "code": null,
                "message": "Transaction successful."
            },
            "transaction_status": {
                "code": "00",
                "name": "Successful",
                "description": "Transaction has been successful"
            },
            "user": {
                "id": 3,
                "type": "BranchAgent",
                "name": "Demo Agent",
                "merchant": {
                    "id": 1,
                    "name": "Demo Merchant"
                }
            },
            "provider_product": {
                "id": 20,
                "product_category_root_id": 1,
                "product": {
                    "id": 20,
                    "name": "Sun Call & Text Combo 50"
                },
                "provider": {
                    "id": 2,
                    "name": "Xpressload"
                }
            }
        }
    ]
}
```

Get all successful transactions of the user and all its branches/agents.

### HTTP Request

`GET http://www.payswitch.net/api/transactions`

### Query Parameters

Parameter | Type | Description
--------- | ---- | -----------
per_page | numeric<br/>(optional) | Number of items per page
page | numeric<br/>(optional) | Page number. Must be present together with per_page.
prod_cat_id | numeric<br/>(optional) | Get only transactions with this prod_cat_id
date_from | date<br/>(optional) | Get transactions starting from this date. Must be present together with date_to. Format: dd/mm/yy.
date_to | date<br/>(optional) | Get transactions until this date. Must be present together with date_from. Format: dd/mm/yy.

### Header Parameters

Parameter | Type | Description
--------- | ------- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token


## Get a Specific Transaction

```shell
curl -X GET
     -H 'X-User-Email: warex03@gmail.com'
     -H 'X-User-Token: _KHS4euMs1At4jsUHHdR'
http://www.payswitch.net/api/transactions/<id>
```

```ruby
require 'net/https'

uri = URI("http://www.payswitch.net/api/transactions/<id>")
http = Net::HTTP.new(uri.host, uri.port)
request_uri = Net::HTTP::Get.new(uri.request_uri)
request_uri.add_field('X-User-Email', 'warex03@gmail.com')
request_uri.add_field('X-User-Token', '_KHS4euMs1At4jsUHHdR')

response = http.request(request_uri)
body = response.body
```

```python
import urllib2

URL = "http://www.payswitch.net/api/transactions/<id>"
HEADERS = {
    'X-User-Email' : 'warex03@gmail.com',
    'X-User-Token' : '_KHS4euMs1At4jsUHHdR'
}

request = urllib2.Request(URL, headers=HEADERS)
response = urllib2.urlopen(request).read()
```

> The JSON return value looks like this:

```json
{
    "id": 1216,
    "payload": {
        "account_id": "4"
    },
    "cost": "15.0",
    "created_at": "2015-02-17T16:14:56.000+08:00",
    "provider_refno": null,
    "provider_message": {
        "code": "3000",
        "message": "MOBILE NUMBER IS INVALID"
    },
    "transaction_status": {
        "code": "08",
        "name": "Invalid cost / amount entered",
        "description": "You have entered an invalid cost / amount for the payload"
    },
    "user": {
        "id": 2,
        "type": "Branch",
        "name": "Demo Branch",
        "merchant": {
            "id": 1,
            "name": "Demo Merchant"
        }
    },
    "provider_product": {
        "id": 502,
        "product_category_root_id": 1,
        "product": {
            "id": 336,
            "name": "Globe 15"
        },
        "provider": {
            "id": 3,
            "name": "Ayannah"
        }
    }
}
```

Get the details of a specific transaction by using transaction id.

### HTTP Request

`GET http://www.payswitch.net/api/transactions/<id>`

### Header Parameters

Parameter | Type | Description
--------- | ------- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token


## Create an E-load Transaction using SKU

```shell
curl -X POST
     -H 'X-User-Email: warex03@gmail.com'
     -H 'X-User-Token: _KHS4euMs1At4jsUHHdR'
     -F "sku=GLOBE15"
     -F "payload[account_id]=09273031099"
http://www.payswitch.net/api/transactions
```

```ruby
require 'net/https'

uri = URI("http://www.payswitch.net/api/transactions")
params = {
  "sku" => "GLOBE15",
  "payload[account_id]" => "09273031099"
}
http = Net::HTTP.new(uri.host, uri.port)
request_uri = Net::HTTP::Post.new(uri.request_uri)
request_uri.add_field('X-User-Email', 'warex03@gmail.com')
request_uri.add_field('X-User-Token', '_KHS4euMs1At4jsUHHdR')
request_uri.set_form_data(params)

response = http.request(request_uri)
body = response.body
```

```python
import urllib2

URL = "http://www.payswitch.net/api/transactions"
HEADERS = {
    'X-User-Email' : 'warex03@gmail.com',
    'X-User-Token' : '_KHS4euMs1At4jsUHHdR'
}
PARAMS = {
    'sku' : 'GLOBE15',
    'payload[account_id]' : '09273031099'
}

data = urllib.urlencode(values)
request = urllib2.Request(URL, data=data, headers=HEADERS)
response = urllib2.urlopen(request).read()
```

> The JSON return value looks like this:

```json
{
    "id": 1552,
    "payload": {
        "account_id": "09273031099"
    },
    "cost": "15.0",
    "created_at": "2015-05-08T10:03:42.423+08:00",
    "provider_refno": null,
    "provider_message": {
        "code": null,
        "message": "Transaction successful."
    },
    "transaction_status": {
        "code": "00",
        "name": "Successful",
        "description": "Transaction has been successful"
    },
    "user": {
        "id": 2,
        "type": "Branch",
        "name": "Demo Branch",
        "merchant": {
            "id": 1,
            "name": "Demo Merchant"
        }
    },
    "provider_product": {
        "id": 619,
        "product_category_root_id": 1,
        "product": {
            "id": 336,
            "name": "Globe 15"
        },
        "provider": {
            "id": 13,
            "name": "Iamax"
        }
    }
}
```

> The JSON return value when you try to fetch a non-existing transactions

```json
[
  {
    "error": "Couldn't find Transaction with id=500"
  }
]
```

Create a transaction by passing the sku and mobile number as payload.

### HTTP Request

`POST http://www.payswitch.net/api/transactions`

### Transaction Payloads

Parameter | Type | Description
--------- | ---- | -----------
sku | string<br/>(required) | The product's SKU code
payload[account_id] | string<br/>(required) | The mobile number of the customer

### Header Parameters

Parameter | Type | Description
--------- | ---- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token


## Create an E-load Transaction using Product ID

```shell
curl -X POST
     -H 'X-User-Email: warex03@gmail.com'
     -H 'X-User-Token: _KHS4euMs1At4jsUHHdR'
     -F "product_id=336"
     -F "payload[account_id]=09273031099"
http://www.payswitch.net/api/transactions
```

```ruby
require 'net/https'

uri = URI("http://www.payswitch.net/api/transactions")
params = {
  "product_id" => 336,
  "payload[account_id]" => "09273031099"
}
http = Net::HTTP.new(uri.host, uri.port)
request_uri = Net::HTTP::Post.new(uri.request_uri)
request_uri.add_field('X-User-Email', 'warex03@gmail.com')
request_uri.add_field('X-User-Token', '_KHS4euMs1At4jsUHHdR')
request_uri.set_form_data(params)

response = http.request(request_uri)
body = response.body
```

```python
import urllib2

URL = "http://www.payswitch.net/api/transactions"
HEADERS = {
    'X-User-Email' : 'warex03@gmail.com',
    'X-User-Token' : '_KHS4euMs1At4jsUHHdR'
}
PARAMS = {
    'product_id' : 336,
    'payload[account_id]' : '09273031099'
}

data = urllib.urlencode(values)
request = urllib2.Request(URL, data=data, headers=HEADERS)
response = urllib2.urlopen(request).read()
```

> The JSON return value looks like this:

```json
{
    "id": 1552,
    "payload": {
        "account_id": "09273031099"
    },
    "cost": "15.0",
    "created_at": "2015-05-08T10:03:42.423+08:00",
    "provider_refno": null,
    "provider_message": {
        "code": null,
        "message": "Transaction successful."
    },
    "transaction_status": {
        "code": "00",
        "name": "Successful",
        "description": "Transaction has been successful"
    },
    "user": {
        "id": 2,
        "type": "Branch",
        "name": "Demo Branch",
        "merchant": {
            "id": 1,
            "name": "Demo Merchant"
        }
    },
    "provider_product": {
        "id": 619,
        "product_category_root_id": 1,
        "product": {
            "id": 336,
            "name": "Globe 15"
        },
        "provider": {
            "id": 13,
            "name": "Iamax"
        }
    }
}
```

Create a transaction by passing the product id and mobile number as payload.

### HTTP Request

`POST http://www.payswitch.net/api/transactions`

### Transaction Payloads

Parameter | Type | Description
--------- | ---- | -----------
product_id | numeric<br/>(required) | The product's id
payload[account_id] | string<br/>(required) | The mobile number of the customer

### Header Parameters

Parameter | Type | Description
--------- | ---- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token