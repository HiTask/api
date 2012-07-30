User
========

Operations related to current user's account: authenticate, sign up, etc.


Authenticate
------------

* `GET /user/authenticate` will authenticate user using user name and password

Input parameters:
* user name
* hashed password

Response:

* id: unique user id used to identify this user account
* level: account level
* session_id: session token

Example request:

```
{
    "api_key" = myapikey;
    login = john;
    password = XXXXXXXXX;
}
```

Example response:
```
{
    id = 12345678;
    level = 300;
    "session_id" = "e0f93451-5ad6-4550-b991-efb0ce1e271b";
}
```


Sign out
------------

* `GET /user/signout` Close user's session.

Input parameters:
* session_id: session token




