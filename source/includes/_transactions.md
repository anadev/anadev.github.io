# Transactions


## Get All Transactions

```shell
curl -X GET
     -H "X-User-Email: warex03@gmail.com"
     -H "X-User-Token: _KHS4euMs1At4jsUHHdR"
     -F "per_page=2"
     -F "page=1"
     -F "prod_cat_id=1"
     -F "date_from=2/2/2015"
     -F "date_to=4/2/2015"
     -F "branch_id=2"
     -F "agent_id=3"
https://www.payswitch.net/api/transactions
```

```ruby
require 'net/https'

uri = URI("https://www.payswitch.net/api/transactions")
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
import requests

URL = "https://www.payswitch.net/api/transactions"
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

response = requests.get(URL, headers=HEADERS, data=PARAMS)
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
                "code": "12345",
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
                "code": "12345",
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
                "code": "12345",
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
                "code": "12345",
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

### V1

`GET https://www.payswitch.net/api/transactions`

### V2

`GET https://www.payswitch.net/api/v2/transactions`


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
https://www.payswitch.net/api/transactions/<id>
```

```ruby
require 'net/https'

uri = URI("https://www.payswitch.net/api/transactions/<id>")
http = Net::HTTP.new(uri.host, uri.port)
request_uri = Net::HTTP::Get.new(uri.request_uri)
request_uri.add_field('X-User-Email', 'warex03@gmail.com')
request_uri.add_field('X-User-Token', '_KHS4euMs1At4jsUHHdR')

response = http.request(request_uri)
body = response.body
```

```python
import urllib2

URL = "https://www.payswitch.net/api/transactions/<id>"
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
    "provider_refno": "12345",
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

`GET https://www.payswitch.net/api/transactions/<id>`

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
https://www.payswitch.net/api/transactions
```

```ruby
require 'net/https'

uri = URI("https://www.payswitch.net/api/transactions")
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

URL = "https://www.payswitch.net/api/transactions"
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
    "provider_refno": "12345",
    "provider_message": {
        "code": "12345",
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

Create a transaction by passing the sku and mobile number as payload.

### HTTP Request

`POST https://www.payswitch.net/api/transactions`

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
https://www.payswitch.net/api/transactions
```

```ruby
require 'net/https'

uri = URI("https://www.payswitch.net/api/transactions")
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

URL = "https://www.payswitch.net/api/transactions"
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
    "provider_refno": "12345",
    "provider_message": {
        "code": "12345",
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

`POST https://www.payswitch.net/api/transactions`

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

## Create a Bills Transaction using SKU

```shell
curl -X POST
     -H 'X-User-Email: warex03@gmail.com'
     -H 'X-User-Token: _KHS4euMs1At4jsUHHdR'
     -F "sku=MAYNILADWATER"
     -F "cost=999"
     -F "payload[field1]=8374638222"
     -F "payload[field2]=Koushirou Sugahara"
     -F "customer[name]=Koushirou Sugahara"
     -F "customer[email]=koushirou_sugahara@armyspy.com"
     -F "customer[contact_number]=09123456789"
     -F "customer[address]=Tokyo Japan"
https://www.payswitch.net/api/transactions
```

```ruby
require 'net/https'

uri = URI("https://www.payswitch.net/api/transactions")
params = {
  "sku" => "MAYNILADWATER",
  "cost" => "999",
  "payload[field1]" => "8374638222",
  "payload[field2]" => "Koushirou Sugahara",
  "customer[name]" => "Koushirou Sugahara",
  "customer[email]" => "koushirou_sugahara@armyspy.com",
  "customer[contact_number]" => "09123456789",
  "customer[address]" => "Tokyo Japan"
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

URL = "https://www.payswitch.net/api/transactions"
HEADERS = {
    'X-User-Email' : 'warex03@gmail.com',
    'X-User-Token' : '_KHS4euMs1At4jsUHHdR'
}
PARAMS = {
    'sku' : 'MAYNILADWATER',
    'cost' : '999',
    'payload[field1]' : '8374638222',
    'payload[field2]' : 'Koushirou Sugahara',
    'customer[name]' : 'Koushirou Sugahara',
    'customer[email]' : 'koushirou_sugahara@armyspy.com',
    'customer[contact_number]' : '09123456789',
    'customer[address]' : 'Tokyo Japan'
}

data = urllib.urlencode(values)
request = urllib2.Request(URL, data=data, headers=HEADERS)
response = urllib2.urlopen(request).read()
```

> The JSON return value looks like this:

```json
{
    "id": 1564,
    "payload": {
        "field1": "12345",
        "field2": "Koushirou Sugahara"
    },
    "cost": "3.0",
    "created_at": "2015-05-15T11:37:09.590+08:00",
    "provider_refno": "12345",
    "provider_message": {
        "code": "12345",
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
        "id": 181,
        "product_category_root_id": 15,
        "product": {
            "id": 183,
            "name": "Maynilad Water Services Inc."
        },
        "provider": {
            "id": 9,
            "name": "Ecpay"
        }
    }
}
```

Create a Bills transaction by passing the sku, cost and account number.

### HTTP Request

`POST https://www.payswitch.net/api/transactions`

Parameter | Type | Description
--------- | ---- | -----------
sku | string<br />(required) | The product's SKU code
cost | string<br />(required) | The bill's amount
payload[field1] | string<br />(required) | The account number of the customer
payload[field2] | string<br />(required) | The customer's name
customer[name] | string<br />(optional) | The customer's name
customer[email] | string<br />(optional) | The customer's email
customer[contact_number] | string<br />(optional) | The customer's contact number
customer[address] | string<br />(optional) | The customer's address

### Header Parameters

Parameter | Type | Description
--------- | ---- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token

## Create a Bills Transaction using product ID

```shell
curl -X POST
     -H 'X-User-Email: warex03@gmail.com'
     -H 'X-User-Token: _KHS4euMs1At4jsUHHdR'
     -F "product_id=183"
     -F "cost=999"
     -F "payload[field1]=8374638222"
     -F "payload[field2]=Koushirou Sugahara"
     -F "customer[name]=Koushirou Sugahara"
     -F "customer[email]=koushirou_sugahara@armyspy.com"
     -F "customer[contact_number]=09123456789"
     -F "customer[address]=Tokyo Japan"
https://www.payswitch.net/api/transactions
```

```ruby
require 'net/https'

uri = URI("https://www.payswitch.net/api/transactions")
params = {
  "product_id" => "183",
  "cost" => "999",
  "payload[field1]" => "8374638222",
  "payload[field2]" => "Koushirou Sugahara",
  "customer[name]" => "Koushirou Sugahara",
  "customer[email]" => "koushirou_sugahara@armyspy.com",
  "customer[contact_number]" => "09123456789",
  "customer[address]" => "Tokyo Japan"
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

URL = "https://www.payswitch.net/api/transactions"
HEADERS = {
    'X-User-Email' : 'warex03@gmail.com',
    'X-User-Token' : '_KHS4euMs1At4jsUHHdR'
}
PARAMS = {
    'product_id' : '183',
    'cost' : '999',
    'payload[field1]' : '8374638222',
    'payload[field2]' : 'Koushirou Sugahara',
    'customer[name]' : 'Koushirou Sugahara',
    'customer[email]' : 'koushirou_sugahara@armyspy.com',
    'customer[contact_number]' : '09123456789',
    'customer[address]' : 'Tokyo Japan'
}

data = urllib.urlencode(values)
request = urllib2.Request(URL, data=data, headers=HEADERS)
response = urllib2.urlopen(request).read()
```

> The JSON return value looks like this:

```json
{
    "id": 1564,
    "payload": {
        "field1": "12345",
        "field2": "Koushirou Sugahara"
    },
    "cost": "3.0",
    "created_at": "2015-05-15T11:37:09.590+08:00",
    "provider_refno": "12345",
    "provider_message": {
        "code": "12345",
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
        "id": 181,
        "product_category_root_id": 15,
        "product": {
            "id": 183,
            "name": "Maynilad Water Services Inc."
        },
        "provider": {
            "id": 9,
            "name": "Ecpay"
        }
    }
}
```

Create a Bills transaction by passing the product id, cost and account number.

### HTTP Request

`POST https://www.payswitch.net/api/transactions`

Parameter | Type | Description
--------- | ---- | -----------
product_id | string<br />(required) | The product's ID
cost | string<br />(required) | The bill's amount
payload[field1] | string<br />(required) | The account number of the customer
payload[field2] | string<br />(required) | The customer's name
customer[name] | string<br />(optional) | The customer's name
customer[email] | string<br />(optional) | The customer's email
customer[contact_number] | string<br />(optional) | The customer's contact number
customer[address] | string<br />(optional) | The customer's address

### Header Parameters

Parameter | Type | Description
--------- | ---- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token

## Create a Mobile Money Transaction using sku

```shell
curl -X POST
     -H 'X-User-Email: warex03@gmail.com'
     -H 'X-User-Token: _KHS4euMs1At4jsUHHdR'
     -F "sku=GCASH_COLLECT"
     -F "cost=999"
     -F "payload[account_id]=09987654321"
     -F "customer[name]=Koushirou Sugahara"
     -F "customer[email]=koushirou_sugahara@armyspy.com"
     -F "customer[contact_number]=09123456789"
     -F "customer[address]=Tokyo Japan"
https://www.payswitch.net/api/transactions
```

```ruby
require 'net/https'

uri = URI("https://www.payswitch.net/api/transactions")
params = {
  "sku" => "GCASH_COLLECT",
  "cost" => "999",
  "payload[account_id]" => "09987654321",
  "customer[name]" => "Koushirou Sugahara",
  "customer[email]" => "koushirou_sugahara@armyspy.com",
  "customer[contact_number]" => "09123456789",
  "customer[address]" => "Tokyo Japan"
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

URL = "https://www.payswitch.net/api/transactions"
HEADERS = {
    'X-User-Email' : 'warex03@gmail.com',
    'X-User-Token' : '_KHS4euMs1At4jsUHHdR'
}
PARAMS = {
    'sku' : 'GCASH_COLLECT',
    'cost' : '999',
    'payload[account_id]' : '09987654321',
    'customer[name]' : 'Koushirou Sugahara',
    'customer[email]' : 'koushirou_sugahara@armyspy.com',
    'customer[contact_number]' : '09123456789',
    'customer[address]' : 'Tokyo Japan'
}

data = urllib.urlencode(values)
request = urllib2.Request(URL, data=data, headers=HEADERS)
response = urllib2.urlopen(request).read()
```

> The JSON return value looks like this:

```json
{
    "id": 1566,
    "payload": {
        "account_id": "09987654321"
    },
    "cost": "1.0",
    "created_at": "2015-05-15T12:33:32.315+08:00",
    "provider_refno": "12345",
    "provider_message": {
        "code": "12345",
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
        "id": 123,
        "product_category_root_id": 12,
        "product": {
            "id": 123,
            "name": "GCash Collect"
        },
        "provider": {
            "id": 4,
            "name": "Gcash"
        }
    }
}
```

Create a Mobile Money transaction by passing the sku, cost and account number.

### HTTP Request

`POST https://www.payswitch.net/api/transactions`

Parameter | Type | Description
--------- | ---- | -----------
sku | string<br />(required) | The product's SKU code
cost | string<br />(required) | The amount of the transaction
payload[account_id] | string<br />(required) | The account number of the customer
customer[name] | string<br />(optional) | The customer's name
customer[email] | string<br />(optional) | The customer's email
customer[contact_number] | string<br />(optional) | The customer's contact number
customer[address] | string<br />(optional) | The customer's address

### Header Parameters

Parameter | Type | Description
--------- | ---- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token


## Create a Mobile Money Transaction using product id

```shell
curl -X POST
     -H 'X-User-Email: warex03@gmail.com'
     -H 'X-User-Token: _KHS4euMs1At4jsUHHdR'
     -F "sku=123"
     -F "cost=999"
     -F "payload[account_id]=09987654321"
     -F "customer[name]=Koushirou Sugahara"
     -F "customer[email]=koushirou_sugahara@armyspy.com"
     -F "customer[contact_number]=09123456789"
     -F "customer[address]=Tokyo Japan"
https://www.payswitch.net/api/transactions
```

```ruby
require 'net/https'

uri = URI("https://www.payswitch.net/api/transactions")
params = {
  "sku" => "123",
  "cost" => "999",
  "payload[account_id]" => "09987654321",
  "customer[name]" => "Koushirou Sugahara",
  "customer[email]" => "koushirou_sugahara@armyspy.com",
  "customer[contact_number]" => "09123456789",
  "customer[address]" => "Tokyo Japan"
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

URL = "https://www.payswitch.net/api/transactions"
HEADERS = {
    'X-User-Email' : 'warex03@gmail.com',
    'X-User-Token' : '_KHS4euMs1At4jsUHHdR'
}
PARAMS = {
    'sku' : '123',
    'cost' : '999',
    'payload[account_id]' : '09987654321',
    'customer[name]' : 'Koushirou Sugahara',
    'customer[email]' : 'koushirou_sugahara@armyspy.com',
    'customer[contact_number]' : '09123456789',
    'customer[address]' : 'Tokyo Japan'
}

data = urllib.urlencode(values)
request = urllib2.Request(URL, data=data, headers=HEADERS)
response = urllib2.urlopen(request).read()
```

> The JSON return value looks like this:

```json
{
    "id": 1566,
    "payload": {
        "account_id": "09987654321"
    },
    "cost": "1.0",
    "created_at": "2015-05-15T12:33:32.315+08:00",
    "provider_refno": "12345",
    "provider_message": {
        "code": "12345",
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
        "id": 123,
        "product_category_root_id": 12,
        "product": {
            "id": 123,
            "name": "GCash Collect"
        },
        "provider": {
            "id": 4,
            "name": "Gcash"
        }
    }
}
```

Create a Mobile Money transaction by passing the product ID, cost and account number.

### HTTP Request

`POST https://www.payswitch.net/api/transactions`

Parameter | Type | Description
--------- | ---- | -----------
product_id | string<br />(required) | The product's ID
cost | string<br />(required) | The amount of the transaction
payload[account_id] | string<br />(required) | The account number of the customer
customer[name] | string<br />(optional) | The customer's name
customer[email] | string<br />(optional) | The customer's email
customer[contact_number] | string<br />(optional) | The customer's contact number
customer[address] | string<br />(optional) | The customer's address

### Header Parameters

Parameter | Type | Description
--------- | ---- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token

## Commit Transaction

```shell
curl -X GET
     -H "X-User-Email: warex03@gmail.com"
     -H "X-User-Token: _KHS4euMs1At4jsUHHdR"
"https://www.payswitch.net/api/transactions/<id>/commit"
```

```ruby
require 'net/https'

uri = URI("https://www.payswitch.net/api/transactions/<id>/commit")
http = Net::HTTP.new(uri.host)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE
request_uri = Net::HTTP::Get.new(uri.request_uri)
request_uri.add_field("X-User-Email", "warex03@gmail.com")
request_uri.add_field("X-User-Token", "_KHS4euMs1At4jsUHHdR")

response = http.request(request_uri)
body = response.body
```

```python
import httplib

URL = "www.payswitch.net"
URI = "/api/transactions/<id>/commit"
HEADERS = {
    "X-User-Email" : "warex03@gmail.com",
    "X-User-Token" : "_KHS4euMs1At4jsUHHdR"
}

conn = httplib.HTTPSConnection(URL)
conn.request("GET", URI, None, HEADERS)
response = conn.getresponse()
data = response.read()
```

> JSON output

```json
{
    "id": 1566,
    "payload": {
        "account_id": "09987654321"
    },
    "cost": "1.0",
    "created_at": "2015-05-15T12:33:32.315+08:00",
    "provider_refno": "12345",
    "provider_message": {
        "code": "12345",
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
        "id": 123,
        "product_category_root_id": 12,
        "product": {
            "id": 123,
            "name": "GCash Collect"
        },
        "provider": {
            "id": 4,
            "name": "Gcash"
        }
    }
}
```

Commit a pending transaction.

### HTTP Request

`GET https://www.payswitch.net/api/transactions/<id>/commit`

### Header Parameters

Parameter | Type | Description
--------- | ---- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token

## Get Revenue Report

```shell
curl -X GET
     -H "X-User-Email: meynardbs@gmail.com"
     -H "X-User-Token: HMMVS-fJe_kLTxK2wfRS"
"https://www.payswitch.net/api/v2/transactions/revenue-report"
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://beta.payswitch.net/api/v2/transactions/revenue-report")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["x-user-email"] = 'meynardbs@gmail.com'
request["x-user-token"] = 'HMMVS-fJe_kLTxK2wfRS'
request.body = "-----011000010111000001101001\r\nContent-Disposition: form-data; name=\"product_id\"\r\n\r\n336\r\n-----011000010111000001101001\r\nContent-Disposition: form-data; name=\"payload[account_id]\"\r\n\r\n09158233358\r\n-----011000010111000001101001\r\nContent-Disposition: form-data; name=\"convenience_fee\"\r\n\r\n2\r\n-----011000010111000001101001--"

response = http.request(request)
puts response.read_body
```

```python
```

> The JSON return value looks like this:

```
{
  "date_from": "2016-04-13T13:30:27.084+08:00",
  "date_to": "2016-04-14T05:30:27+00:00",
  "revenue_reports": [],
  "total_transaction_cost": 0,
  "total_convenience_fee": 0,
  "total_revenue": 0,
  "transactions": []
}
```

Get revenue report based on number of transactions for the last 24 hours

### HTTP Request

`GET https://www.payswitch.net/api/v2/transactions/revenue-report`

### Header Parameters

Parameter | Type | Description
--------- | ---- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token
