# Introduction

KATSANA API allows everyone to build apps on the KATSANA Platform. Our API is organized around REST. JSON will be returned in all responses from the API, including errors.

# Getting Started

Let's walk through core API concepts as we tackle some everyday use cases.

## API Information

To get started, you can first try out our default welcome API, which would return the current Platform version and list of supported API versions.

```bash
curl https://api.katsana.com -X GET
```

```json
{
    "platform": "v4.3.0",
    "api": [
        "v1"
    ]
}
```

## Request Headers

KATSANA API would require all API endpoint to include the following **HTTP Request Headers** all versioned API endpoint which requires authentication.

```bash
curl https://api.katsana.com
     -X GET 
     -H "Accept: application/vnd.KATSANA.v1+json" 
     -H "Authorization: Bearer {{access-token}}"
```

| Type          | Value
|:--------------|:--------
| Accept        | application/vnd.KATSANA.v1+json
| Authorization | Bearer {{access-token}}


Please read on [Authentication](#authentication) to learn on how to obtain `{{access-token}}` for a particular user.

# Authentication

In this section, we're going to focus on the basics of authentication. 

# Users 

## Show Profile

```bash
curl https://api.katsana.com/profile
     -X GET 
     -H "Accept: application/vnd.KATSANA.v1+json" 
     -H "Authorization: Bearer {{access-token}}"
```

```json
{
    "id": 1,
    "email": "hello@katsana.com",
    "phone_home": "0123456789",
    "phone_mobile": "0123456789",
    "fullname": "Katsana User",
    "meta": {
        "emergency": {
            "fullname": "",
            "phone": {
                "home": "",
                "mobile": ""
            }
        }
    },
    "avatar": null,
    "timezone": "Asia/Kuala_Lumpur",
    "created_at": "2015-09-06 11:06:45",
    "updated_at": "2015-09-06 11:06:45"

}
```


### HTTP REQUEST

`GET /profile`

## Update Profile

### HTTP REQUEST

`POST /profile`
