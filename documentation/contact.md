Contact
========

Operations with user's contacts: add, remove, list contacts


Get list of user's contacts
------------

* `GET 	/contact` will return list of user's contacts

### Parameters
<table>
    <tr>
        <th>Parameter</th>
        <th>Type</th>
        <th>Description</th>
    </tr>
    <tr>
        <td><code>includeSelf</code></td>
        <td>1 or 0</td>
        <td>Include current user.</td>
    </tr>
</table>

### Example response

```js
{
email: "user@email.com"
emailConfirmed: "user@email.com"
firstName: "John"
id: 123
isOnline: false
lastName: "Jackson"
level: 100
login: "john"
pictureHash: "267744510460b6ec63453483f725252"
subscription: "BOTH"
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
        <td>Globally unique primary identifier for a contact.</td>
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
        <td><code>pictureHash</code></td>
        <td>String</td>
        <td>Unique address of user's avatar picture. <br/>To display the picture following URL composition should be used:<br/>
        [http|https]://htiask.com/avatar/[pictureHash].[pixel size].gif
        <br/>where pixel size is one of 16,40,64,80
</td>
    </tr>
    <tr>
        <td><code>subscription</code></td>
        <td>String</td>
        <td>Designates if contact request is sent or receved or if relationship is established.<br/>
      Can be one of: FROM, TO, BOTH.<br/>BOTH means contact relationship is established.
FROM means request from this contact is received. TO means request was sent and we're waiting for user to accept.
SELF means this is the current user.
</td>
    </tr>
</table>



Add contact
------------

* `POST	/contact`


Delete
------------

* `DELETE	/contact` 


Search
------------

* `GET		/contact/search` find contact by name or email


Invite
------------

* `GET     /contact/invite` Invite contact to create an account


Approve invitation
------------

* `GET     /contact/approve` Approve invitation/connection



Add contact to Business account
------------

* `GET		/contact/addtobusiness` will add contact as member of Business account


Remove contact from Business account
------------

* `GET		/contact/removefrombusiness` will add contact as member of Business account
