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

* `GET /user/signout` Close user's session.

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
        <td><code>level</code></td>
        <td>integer</td>
        <td>user's account level: 0: Free, 50: Premium, 100: Business</td>
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
* firstName: First Name
* lastName: Last Name
* email: e-mail address. If email address is different from previously stored, an email message with address confirmation will be sent
