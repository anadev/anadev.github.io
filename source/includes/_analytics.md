# Analytics

## Get Transaction Sales

```shell
curl -X GET
     -H "X-User-Email: meynardbs@gmail.com"
     -H "X-User-Token: HMMVS-fJe_kLTxK2wfRS"
"https://beta.payswitch.net/api/v2/analytics/sales"
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://beta.payswitch.net/api/v2/analytics/sales")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["x-user-email"] = 'meynardbs@gmail.com'
request["x-user-token"] = 'HMMVS-fJe_kLTxK2wfRS'

response = http.request(request)
puts response.read_body
```

```python

```

> The JSON return value looks like this:

```
{
  "labels": [
    "Apr 07",
    "Apr 08",
    "Apr 09",
    "Apr 10",
    "Apr 11",
    "Apr 12",
    "Apr 13",
    "Apr 14"
  ],
  "data": [
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0
  ]
}
```
Get weekly or monthly sales of the user

### HTTP Request

`GET https://www.payswitch.net/api/v2/analytics/sales`

### Header Parameters

Parameter | Type | Description
--------- | ------- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token

### Query Parameters

Parameter | Type | Description
--------- | ---- | -----------
duration  | string</br>(optional) | Frequency of transaction sales.</br>(weekly or monthly)
