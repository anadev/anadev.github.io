# Authentication

```shell
curl -X POST
     -F "user[email]=meynardbs@gmail.com"
     -F "user[password]=password"
     -F "grant_type=password"
"https://try.payswitch.net/oauth/token"
```

```ruby
require 'net/https'

uri = URI("https://try.payswitch.net/oauth/token")
params = {
  user: {
    email: 'meynarddbs@gmail.com',
    password: 'password'
  },
  grant_type: 'password'
}
uri.query = URI.encode_www_form(params)

http = Net::HTTP.new(uri.host, uri.port)
request_uri = Net::HTTP::Get.new(uri.request_uri)

response = http.request(request_uri)
```

```python
import requests

URL = "https://try.payswitch.net/oauth/token"
PARAMS = {
  'user[email]' : 'meynarddbs@gmail.com',
  'user[password]' : 'password',
  'grant_type' : 'password'
}

response = requests.post(URL, data=PARAMS)
```

> JSON Response

```json
{
    "access_token": "3acd3ea74424aa3f4a18d6f8e42a0f02e49177c5862a976f4ca3a5b439c8be13",
    "token_type": "bearer",
    "expires_in": 86400,
    "created_at": 1460608249
}
```

Authentication to the API can be done via OAuth 2. After getting the OAuth token, set the `Authorization`
header to `Bearer<space><token>` where token is the one you got from this request.

When you authenticate via bearer auth, you no longer need to set `X-User-Email` and `X-User-Token` headers.

### HTTP Request

`POST https://try.payswitch.net/oauth/token`

### Form Parameters

Parameter      | Type                  | Description
-------------- | --------------------- | ------------------------
user[email]    | string</br>(required) | The user's email address
user[password] | string</br>(required) | The user's password
grant_type     | string</br>(required) | Always use `password`
