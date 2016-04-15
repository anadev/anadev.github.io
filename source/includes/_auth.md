# Authentication Token

## Get Session Token

```shell
curl -X POST 
     -F "user[email]=meynardbs@gmail.com" 
     -F "user[password]=password" 
     -F "grant_type=password" 
"https://www.payswitch.net/oauth/token"
```

```ruby

```

```python


```
> JSON Output

```json
{
    "access_token": "3acd3ea74424aa3f4a18d6f8e42a0f02e49177c5862a976f4ca3a5b439c8be13",
    "token_type": "bearer",
    "expires_in": 86400,
    "created_at": 1460608249
}

```
Get session token of the user

### HTTP Request

`POST https://www.payswitch.net/oauth/token`

### Form Parameters

Parameter | Type | Description
--------- | ---- | -----------
user[email] | string</br>(required) | The user's email address
user[password] | string</br>(required) | The user's password
grant_type | string</br>(required) | Always use `password`


