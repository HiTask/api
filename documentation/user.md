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
    businessId : 123;
    businessLevel : 100;
	email : "name@gmail.com";
	emailConfirmed : "name@gmail.com";
	id : 123;
	isOnline : 1;
	level : 0;
	login : john;
	firstName : Mick;
	lastName : Johnson;
}
```

### Response fields:

<table>
    <tr>
        <th>Field</th>
        <th>Type</th>
        <th>Description</th>
    </tr>
    <tr>
        <td><code>id</code></td>
        <td>long</td>
        <td>Globally unique primary identifier for a user. This is an integer, but it is recommended to handle it as String to avoid limitations with the way JavaScript integers are expressed.</td>
    </tr>
    <tr>
        <td><code>accountType</code></td>
        <td>String</td>
        <td>User's account type: <code>TEAM_BASIC, TEAM_BUSINESS, PERSONAL_FREE, PERSONAL_PREMIUM</code></td>
    </tr> 
    <tr>
        <td><code>login</code></td>
        <td>String</td>
        <td>user login id</td>
    </tr>
    <tr>
        <td><code>firstName</code></td>
        <td>String</td>
        <td>user's First Name</td>
    </tr>
    <tr>
        <td><code>lastName</code></td>
        <td>String</td>
        <td>user's Last Name</td>
    </tr>
    <tr>
        <td><code>emailConfirmed</code></td>
        <td>String</td>
        <td>Email address that was confirmed by the user. (By clicking confirmaiton link sent to this email address.)</td>
    </tr>
    <tr>
        <td><code>email</code></td>
        <td>String</td>
        <td>Email address that user entered but not confirmed. Do not send emails to this address as it may not be confirmed.</td>
    </tr>
    <tr>
        <td><code>businessId</code></td>
        <td>Integer</td>
        <td>unique identifier of user's Business group account, if applicable </td>
    </tr>
    <tr>
        <td><code>businessLevel</code></td>
        <td>Integer</td>
        <td>MEmbership level of user in Business account</td>
    </tr>
</table>





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

## Update User Avatar

* `DELETE /user/picture`  Update current user avatar

Input parameters:
* returninfo: (optional) if "true" then full account info will be returned as described in `GET /user`
