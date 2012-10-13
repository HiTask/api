# User

Operations related to current user's account: authenticate, sign up, etc.

## Authenticate


* `GET /user/authenticate` will authenticate user using user name and password

Input parameters:
* user name
* hashed password

Response values:

* id: unique user id used to identify this user account
* level: account level
* session_id: session token

### Example request:

```js
{
    "api_key" = myapikey;
    login = john;
    password = XXXXXXXXX;
}
```

### Example response:

```js
{
    id = 12345678;
    level = 300;
    "session_id" = "e0f93451-5ad6-4550-b991-efb0ce1e271b";
}
```


## Sign out

End current session

* `GET /user/signout` Close user's session.

Input parameters:
* session_id: session token


## User Account information

* `GET /user`  Get current user acocutn information

### Example response:

```js
{
    businessId = 123;
    businessLevel = 100;
	email = "name@gmail.com";
	emailConfirmed = "name@gmail.com";
	id = 123;
	isOnline = 1;
	level = 0;
	login = john;
	firstName = Mick;
	lastName = Johnson;
}
```

Response:

* businessId: id of Business group acocunt, if applicable
* businessLevel: Business accoutn member level
* email: user's email address
* emailConfirmed: user's email address
* id: global unique user id
* isOnline: user's online status
* level: user's accoutn level: 0: Free, 50: Premium, 100: Business
* login: user login id
* firstName, lastName: first and last name
