# Wallet

## Get Wallet Ledger

```shell
curl -X GET 
    -H "X-User-Email: meynardbs@gmail.com" 
    -H "X-User-Token: HMMVS-fJe_kLTxK2wfRS" 
"https://try.payswitch.net/api/v2/wallet/ledger"
```

```python

```

```ruby
require 'uri'
require 'net/http'

url = URI("https://try.payswitch.net/api/v2/wallet/ledger")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["x-user-email"] = 'meynardbs@gmail.com'
request["x-user-token"] = 'HMMVS-fJe_kLTxK2wfRS'

response = http.request(request)
puts response.read_body
```
> JSON Output

```json
{
    "date_from":"2016-04-17T13:53:50.553+08:00",
    "date_to":"2016-04-18T05:53:50+00:00",
    "total_debit_amount":0.0,
    "total_credit_amount":0.0,
    "amounts":[]
}
```
Get wallet ledger of the current user

### HTTP Request

`GET https://try.payswitch.net/api/v2/wallet/ledger`

### Header Parameters

Parameter | Type | Description
--------- | ------- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token
