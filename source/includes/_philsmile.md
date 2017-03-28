# Philsmile

## Get schools

```shell
curl -X GET
     -H 'X-User-Email: warex03@gmail.com'
     -H 'X-user-Token: _KHS4euMs1At4jsUHHdR'
https://try.payswitch.net/api/philsmile/schools
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://try.payswitch.net/api/philsmile/schools")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["x-user-email"] = 'warex03@gmail.com'
request["x-user-token"] = '_KHS4euMs1At4jsUHHdR'

response = http.request(request)
puts response.read_body
```

```python
import urllib, httplib

URL = "www.payswitch.net"
URI = "/api/philsmile/schools"
HEADERS = {
    "X-User-Email" : "warex03@gmail.com",
    "X-User-Token" : "_KHS4euMs1At4jsUHHdR"
}

conn = httplib.HTTPSConnection(URL)
conn.request("GET", URI, HEADERS)
response = conn.getresponse()
data = response.read()
```

> JSON output sample

```json
[
  {
    "school_id": 1738,
    "school_name": "Most Institute Culinary School",
    "status": "signed"
  },
  {
    "school_id": 3211,
    "school_name": "Child Learning Foundation - Cebu",
    "status": "signed"
  },
  {
    "school_id": 3280,
    "school_name": "Jesus Reigns Christian Academy Caloocan Campus",
    "status": "signed"
  }
]
```

Get all the available schools

### HTTPS REQUEST

`GET https://try.payswitch.net/api/philsmile/schools`

### PERMISSIONS

User Type | Has access | Description
--------- | ---------- | -----------
Merchant | TRUE | All agents under its branches.
Branch | TRUE | All agents under the branch.
Agent | TRUE | All agents under the branch.

### School status

Status | Description
-------| -----------
Signed | Has no access to bills data
Active | Has access to bills data


## Get bills

```shell
curl -X GET
     -H "X-User-Email: warex03@gmail.com"
     -H "X-User-Token: _KHS4euMs1At4jsUHHdR"
     -F "schoolid=1738"
     -F "studentid=14300006"
https://try.payswitch.net/api/philsmile/bills
```

```ruby
require 'uri'
require 'net/http'

uri = URI("https://try.payswitch.net/api/philsmile/bills")

params = {
  schooldid: 1738,
  studentid: 14300006
}
uri.query = URI.encode_www_form(params)

http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request_uri = Net::HTTP::Get.new(url.request_uri)
request_uri["x-user-email"] = 'warex03@gmail.com'
request_uri["x-user-token"] = '_KHS4euMs1At4jsUHHdR'


response = http.request(request_uri)
body = response.body
```

```python
import urllib, httplib

URL = "www.payswitch.net"
URI = "/api/philsmile/bills"
HEADERS = {
    "X-User-Email" : "warex03@gmail.com",
    "X-User-Token" : "_KHS4euMs1At4jsUHHdR"
}
DATA = {
  "schoolid": "1738",
  "studentid": "14300006"
}

conn = httplib.HTTPSConnection(URL)
conn.request("GET", URI, DATA, HEADERS)
response = conn.getresponse()
data = response.read()
```

> JSON output

```json
{
  "ps_txn_id": "PSS-00003631-00000357",
  "bills": [
    {
      "item_id": "14300006-Midterm",
      "item_name": "Midterm",
      "item_description": "Midterm",
      "status": "unpaid",
      "due_date": 1438272000,
      "fee": {
        "amount": "550.00",
        "currency": "PHP"
      },
      "fee_forex": {
        "amount": "550.00",
        "currency": "PHP"
      },
      "remaining": {
        "amount": "550.00",
        "currency": "PHP"
      },
      "remaining_forex": {
        "amount": "550.00",
        "currency": "PHP"
      }
    },
    {
      "item_id": "14300006-Finals",
      "item_name": "Finals",
      "item_description": "Finals",
      "status": "paid",
      "due_date": 1438272000,
      "fee": {
        "amount": "1137.00",
        "currency": "PHP"
      },
      "fee_forex": {
        "amount": "1137.00",
        "currency": "PHP"
      },
      "remaining": {
        "amount": "0.00",
        "currency": "PHP"
      },
      "remaining_forex": {
        "amount": "0.00",
        "currency": "PHP"
      }
    }
  ],
  "student": {
    "first_name": "Winifred",
    "last_name": "Garcia",
    "student_number": "14300006",
    "campus": "Quezon City",
    "school_year": 2015,
    "term": 1,
    "year_level": 2,
    "program": "BM"
  }
}
```

Get school bills of the customer. This is not required for signed schools.

### HTTP REQUEST

`GET https://try.payswitch.net/api/philsmile/bills`

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
Agent | TRUE | All agents under the branch.

### QUERY PARAMETERS

Key | Description
----| -----------
schoolid | School id from the list of school
studentid | Student id of the customer

## Get fees

```shell
curl -X GET
     -H "X-User-Email: warex03@gmail.com"
     -H "X-User-Token: _KHS4euMs1At4jsUHHdR"
     -F "ps_txn_id=PSS-00003631-00000357"
     -F "bill_id=14300006-Midterm"
https://try.payswitch.net/api/philsmile/fee
```

```ruby
require 'uri'
require 'net/http'

uri = URI("https://try.payswitch.net/api/philsmile/fee")

params = {
  ps_txn_id: "PSS-00003631-00000357",
  bill_id: "14300006-Midterm"
}
uri.query = URI.encode_www_form(params)

http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request_uri = Net::HTTP::Get.new(url.request_uri)
request_uri["x-user-email"] = 'warex03@gmail.com'
request_uri["x-user-token"] = '_KHS4euMs1At4jsUHHdR'


response = http.request(request_uri)
body = response.body
```

```python
import urllib, httplib

URL = "www.payswitch.net"
URI = "/api/philsmile/fee"
HEADERS = {
    "X-User-Email" : "warex03@gmail.com",
    "X-User-Token" : "_KHS4euMs1At4jsUHHdR"
}
DATA = {
  "ps_txn_id": "PSS-00003631-00000357",
  "bill_id": "14300006-Midterm"
}

conn = httplib.HTTPSConnection(URL)
conn.request("GET", URI, DATA, HEADERS)
response = conn.getresponse()
data = response.read()
```

> JSON output

```json
{
  "sender_fee": "10.00",
  "total": "550.00",
  "ps_txn_id": "PSS-00003631-00000357"
}
```

Get all the current fees from the school

### HTTP REQUEST

`GET https://try.payswitch.net/api/philsmile/fees`

### PERMISSIONS

User Type | Has access | Description
--------- | ---------- | -----------
Merchant | TRUE | All agents under its branches.
Branch | TRUE | All agents under the branch.
Agent | TRUE | All agents under the branch.

### QUERY PARAMETERS
Key | Description
----|------------
ps_txn_id | You can get the value for this parameter from the get bills API call.
bill_id | The value of this parameter is the value of item id from the get bills API call.
