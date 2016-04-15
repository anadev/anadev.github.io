# Branches

## Get All Branches

```shell
curl -X GET
     -H 'X-User-Email: warex03@gmail.com'
     -H 'X-User-Token: _KHS4euMs1At4jsUHHdR'
http://www.payswitch.net/api/branches
```

```ruby
require 'net/https'

uri = URI("http://www.payswitch.net/api/branches")

http = Net::HTTP.new(uri.host, uri.port)
request_uri = Net::HTTP::Get.new(uri.request_uri)
request_uri.add_field('X-User-Email', 'warex03@gmail.com')
request_uri.add_field('X-User-Token', '_KHS4euMs1At4jsUHHdR')

response = http.request(request_uri)
body = response.body
```

```python
import requests

URL = "http://www.payswitch.net/api/branches"
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
```

Get the list of branches.

### HTTP REQUEST

`GET http://www.payswitch.net/api/branches`

### HEADER PARAMETERS

Parameter | Type | Description
--------- | ------- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token

### PERMISSIONs

User Type | Has access | Description
--------- | ---------- | -----------
Merchant | TRUE | All agents under its branches.
Branch | FALSE | Permission error message
Agent | FALSE | Permission error message

## Get All Branches with Agents

```shell
curl -X GET
     -H 'X-User-Email: warex03@gmail.com'
     -H 'X-User-Token: _KHS4euMs1At4jsUHHdR'
http://www.payswitch.net/api/branches/agents
```

```ruby
require 'net/https'

uri = URI("http://www.payswitch.net/api/branches/agents")

http = Net::HTTP.new(uri.host, uri.port)
request_uri = Net::HTTP::Get.new(uri.request_uri)
request_uri.add_field('X-User-Email', 'warex03@gmail.com')
request_uri.add_field('X-User-Token', '_KHS4euMs1At4jsUHHdR')

response = http.request(request_uri)
body = response.body
```

```python
import requests

URL = "http://www.payswitch.net/api/branches/agents"
HEADERS = {
    'X-User-Email' : 'warex03@gmail.com',
    'X-User-Token' : '_KHS4euMs1At4jsUHHdR'
}

response = requests.get(URL, headers=HEADERS)
```

> JSON output for Merchant

```json
[
    {
        "id": 2,
        "name": "Demo Branch",
        "branch_agents": [
            {
                "id": 3,
                "email": "agent@demomerchant.com",
                "branch_id": 2,
                "name": "Demo Agent",
                "contact_number": "9302107",
                "banned": false,
                "balance": "27.0"
            },
            {
                "id": 8,
                "email": "agent2@demomerchant.com",
                "branch_id": 2,
                "name": "Demo 2 Payswitch",
                "contact_number": "09209876543",
                "banned": false,
                "balance": "240.0"
            }
        ]
    },
    {
        "id": 51,
        "name": "Sample Branch",
        "branch_agents": [
            {
                "id": 53,
                "email": "sample_agent@demomerchant.com",
                "branch_id": 51,
                "name": "Sample Agent",
                "contact_number": "09222456789",
                "banned": false,
                "balance": "0.0"
            }
        ]
    }
]
```

> JSON output for Branch

```json
[
    {
        "id": 2,
        "name": "Demo Branch",
        "branch_agents": [
            {
                "id": 3,
                "email": "agent@demomerchant.com",
                "branch_id": 2,
                "name": "Demo Agent",
                "contact_number": "9302107",
                "banned": false,
                "balance": "27.0"
            },
            {
                "id": 8,
                "email": "agent2@demomerchant.com",
                "branch_id": 2,
                "name": "Demo 2 Payswitch",
                "contact_number": "09209876543",
                "banned": false,
                "balance": "240.0"
            }
        ]
    }
]
```

Get all branches with agents when current user is a Merchant

Get ID, name and its agents when current user is a Branch

### HTTP REQUEST

`GET http://www.payswitch.net/api/branches/agents`

### HEADER PARAMETERS

Parameter | Type | Description
--------- | ------- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token


### PERMISSIONS

User Type | Has access | Description
--------- | ---------- | -----------
Merchant | TRUE | All branches with its agents.
Branch | TRUE | ID, Name and its agents.
Agent | FALSE | Permission error message


## Get Branch Details

```shell
curl -X GET
     -H 'X-User-Email: warex03@gmail.com'
     -H 'X-User-Token: _KHS4euMs1At4jsUHHdR'
http://www.payswitch.net/api/branches/2
```

```ruby
require 'net/https'

uri = URI("http://www.payswitch.net/api/branches/2")

http = Net::HTTP.new(uri.host, uri.port)
request_uri = Net::HTTP::Get.new(uri.request_uri)
request_uri.add_field('X-User-Email', 'warex03@gmail.com')
request_uri.add_field('X-User-Token', '_KHS4euMs1At4jsUHHdR')

response = http.request(request_uri)
body = response.body
```

```python
import requests

URL = "http://www.payswitch.net/api/branches/2"
HEADERS = {
    'X-User-Email' : 'warex03@gmail.com',
    'X-User-Token' : '_KHS4euMs1At4jsUHHdR'
}

response = requests.get(URL, headers=HEADERS)
```

> JSON output

```json
{
    "id": 2,
    "email": "branch@demomerchant.com",
    "merchant_id": 1,
    "name": "Demo Branch",
    "contact_number": "09273031099",
    "banned": false,
    "balance": "19.0",
    "branch_agents": [
        {
            "id": 3,
            "email": "agent@demomerchant.com",
            "branch_id": 2,
            "name": "Demo Agent",
            "contact_number": "9302107",
            "banned": false,
            "balance": "27.0"
        },
        {
            "id": 8,
            "email": "agent2@demomerchant.com",
            "branch_id": 2,
            "name": "Demo 2 Payswitch",
            "contact_number": "09209876543",
            "banned": false,
            "balance": "240.0"
        },
        {
            "id": 13,
            "email": "meynardbs@gmail.com",
            "branch_id": 2,
            "name": "Meynard Soriano",
            "contact_number": "09055726144",
            "banned": false,
            "balance": "0.0"
        },
        {
            "id": 18,
            "email": "branch3@local.host",
            "branch_id": 2,
            "name": "Branch Three",
            "contact_number": "09201234567",
            "banned": false,
            "balance": "195.0"
        }
    ]
}
```

> The JSON return value when you try to fetch a non-existing branch

```json
[
	{
	  "success": false,
	  "message": "Branch user not found"
	}
]
```

Get the details of a branch and its agents

### HTTP REQUEST

`GET http://www.payswitch.net/api/branches/<id>`

### HEADER PARAMETERS

Parameter | Type | Description
--------- | ---- | -----------   
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token

### PERMISSIONS

User Type | Has access | Description
--------- | ---------- | -----------
Merchant | TRUE | Return agent details.
Branch | FALSE | Permission error message.
Agent | FALSE | Permission error message.
