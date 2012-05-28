HiTask API
====================


JSON
-----------------

We only support JSON for serialization of data. Output format is data as root element.


Error handling
---------------

You need to check HTTP status in case there's an error. Basic rule is to check that code is not 200. If it's not 200 then expanded error code and error message will be in Json data.


Rate limiting
-------------

You can perform up to 200 requests per 10 second period from the same IP address for the same account. If you exceed this limit you will have to wait before your next request is processed.


API endpoints
-----------------

* [User](https://github.com/hitask/api/blob/master/documentation/user.md)
* [Item (task, event, note, project)](https://github.com/hitask/api/blob/master/documentation/item.md)
* [Contact](https://github.com/hitask/api/blob/master/documentation/contact.md)
