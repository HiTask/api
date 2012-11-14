Contact
========

Operations with user's contacts: add, remove, list contacts


Get list of user's contacts
------------

* `GET 	/contact` will return list of user's contacts

```js
{
"level":0,
"subscription":"BOTH",
"isOnline":false,
"id":321,
"email":"user@email.com"
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