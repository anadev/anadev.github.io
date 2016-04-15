# Agents

## Get All Agents

```shell
curl -X GET
     -H 'X-User-Email: warex03@gmail.com'
     -H 'X-User-Token: _KHS4euMs1At4jsUHHdR'
http://www.payswitch.net/api/agents
```

```ruby
require 'net/https'

uri = URI("http://www.payswitch.net/api/agents")

http = Net::HTTP.new(uri.host, uri.port)
request_uri = Net::HTTP::Get.new(uri.request_uri)
request_uri.add_field('X-User-Email', 'warex03@gmail.com')
request_uri.add_field('X-User-Token', '_KHS4euMs1At4jsUHHdR')

response = http.request(request_uri)
body = response.body
```

```python
import requests

URL = "http://www.payswitch.net/api/agents"
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
        "id": 3,
        "created_at": "2014-09-10T13:32:59.000+08:00",
        "branch_id": 2,
        "name": "Demo Agent",
        "contact_number": null,
        "balance": "345.0"
    },
    {
        "id": 8,
        "created_at": "2014-09-24T17:26:38.000+08:00",
        "branch_id": 2,
        "name": "Demo 2 Payswitch",
        "contact_number": "09201234567",
        "balance": "1000.0"
    },
    {
        "id": 18,
        "created_at": "2014-11-05T07:38:07.000+08:00",
        "branch_id": 2,
        "name": "Branch Three",
        "contact_number": "09201234567",
        "balance": "195.0"
    }
]
```

Get the list of all agents

### HTTP REQUEST

`GET http://www.payswitch.net/api/agents`

### HEADER PARAMETERS

Parameter | Type | Description
--------- | ------- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token


### PERMISSIONS

User Type | Has access | Description
--------- | ---------- | -----------
Merchant | TRUE | All agents under its branches.
Branch | TRUE | All agents under the branch.
Agent | FALSE | Permission error message

## Get Agent Details

```shell
curl -X GET
     -H 'X-User-Email: warex03@gmail.com'
     -H 'X-User-Token: _KHS4euMs1At4jsUHHdR'
http://www.payswitch.net/api/agents/8
```

```ruby
require 'net/https'

uri = URI("http://www.payswitch.net/api/agents/8")

http = Net::HTTP.new(uri.host, uri.port)
request_uri = Net::HTTP::Get.new(uri.request_uri)
request_uri.add_field('X-User-Email', 'warex03@gmail.com')
request_uri.add_field('X-User-Token', '_KHS4euMs1At4jsUHHdR')

response = http.request(request_uri)
body = response.body
```

```python
import requests

URL = "http://www.payswitch.net/api/agents/8"
HEADERS = {
    'X-User-Email' : 'warex03@gmail.com',
    'X-User-Token' : '_KHS4euMs1At4jsUHHdR'
}

response = requests.get(URL, headers=HEADERS)
```

> JSON output

```json
{
    "id": 8,
    "email": "agent2@demomerchant.com",
    "branch_id": 2,
    "name": "Demo 2 Payswitch",
    "contact_number": "09209876543",
    "banned": false,
    "balance": "240.0"
}
```

> The JSON return value when you try to fetch a non-existing agent

```json
[
  {
    "success": false,
    "message": "Agent user not found."
  }
]
```

Get the details of an agent given its id.

### HTTP REQUEST

`GET http://www.payswitch.net/api/agents/<id>`

### HEADER PARAMETERS

Parameter | Type | Description
--------- | ---- | -----------   
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token

### PERMISSIONS

User Type | Has access | Description
--------- | ---------- | -----------
Merchant | TRUE | Return agent details.
Branch | TRUE | Return agent details.
Agent | FALSE | Permission error message.
