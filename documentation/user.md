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
    "api_key" : myapikey;
    login : john;
    password : XXXXXXXXX;
}
```

### Example response:

```js
{
    id : 12345678;
    level : 300;
    "session_id" : "e0f93451-5ad6-4550-b991-efb0ce1e271b";
}
```


## Sign out

End current session

* `GET /user/logout` Close user's session.

Input parameters:
* session_id: session token


## User Account information

* `GET /user`  Get current user account information

### Example response:

```js
{
    businessId : 123,
    businessLevel : 100,
	email : "name@gmail.com",
	emailConfirmed : "name@gmail.com",
	id : 123,
	isOnline : 1,
	level : 0,
	login : "john",
	firstName : "Mick",
	lastName : "Johnson",
	pictureSource: 1000,
	pictureHash: "4b0c75c8-14cc-49b2-80aa-b49f5cf62daf"
}
```

### Response fields:

|Field|Type|Description|
|-----|----|-----------|
|<code>id</code>|long|Globally unique primary identifier for a user. This is an integer, but it is recommended to handle it as String to avoid limitations with the way JavaScript integers are expressed.|
|<code>accountType</code>|String|User's account type: <code>TEAM_BASIC, TEAM_BUSINESS, PERSONAL_FREE, PERSONAL_PREMIUM</code></
    |><code>login</code>|String|user login id|
|<code>firstName</code>|String|user's First Name|
|<code>lastName</code>       |String        |user's Last Name|
|<code>emailConfirmed</code>        |String        |Email address that was confirmed by the user. (By clicking confirmaiton link sent to this email address.)|
|<code>email</code>        |String        |Email address that user entered but not confirmed. Do not send emails to this address as it may not be confirmed.|
|<code>businessId</code>        |Integer        |unique identifier of user's Business group account, if applicable |
|<code>businessLevel</code>        |Integer        |MEmbership level of user in Business account|
|<code>pictureHash</code>        |String        |Unique avatar identifier that should be used in order to build user avatar URL|
|<code>pictureSource</code>|Integer| Type of user avatar: See below  |

#### Type of user avatar

* 0 Avatar is missing (only happens if generation failed)
* 1 Avatar is auto-generating (searching social sources or auto generating: only happens if user registered few seconds ago)
* 2 Auto generated (initials on background)
* 10 Google
* 11 Facebook
* 12 Gravatar
* 100 User uploaded
* 1000 Unknown|
    





## Update User Account information

* `PUT /user`  Update current user account information

Input parameters:
* firstname: First Name
* lastname: Last Name
* email: e-mail address. If email address is different from previously stored, an email message with address confirmation will be sent


## Update User Avatar

* `POST /user/picture`  Update current user avatar

Input parameters:
* picture: Picture data
* x: (Optional) X coordinate of top left corner of square that will be used to crop the picture (x, y and width must be specified to crop the picture)
* y: (Optional) Y coordinate of top left corner of square that will be used to crop the picture (x, y and width must be specified to crop the picture)
* width: (Optional) Width of square that will be used to crop the picture (x, y and width must be specified to crop the picture)

Restrictions:
* max picture size is 1MB
* allowed picture formats: "gif", "jpeg", "jpg", "png"

Error codes:
* HTTP 400 and code 32: picture upload failed, retry required
* HTTP 400 and code 34: crop parameters are invalid
* HTTP 400 and code 6: uploaded data is not a valid picture
* HTTP 400 and code 5: picture format is not valid
* HTTP 400 and code 25: picture exceeded maximum allowed size

Response:

JSON object with one property "hash": unique picture identifier.

```js
{"hash":"4b0c75c8-14cc-49b2-80aa-b49f5cf62daf"}
```

## Delete User Avatar

* `DELETE /user/picture`  Delete current user avatar

Input parameters:
* returninfo: (optional) if "true" then full account info will be returned as described in `GET /user`
