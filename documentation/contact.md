Contact
========

Operations with user's contacts: add, remove, list contacts


Get list of user's contacts
------------

* `GET 	/contact` will return list of user's contacts

```js
{
email: "user@email.com"
emailConfirmed: "user@email.com"
firstName: "John"
id: 123
isOnline: false
isPremium: true
lastName: "Jackson"
level: 100
login: "John"
pictureHash: "267744510460b6ec63453483f725252"
subscription: "BOTH"
}
```


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