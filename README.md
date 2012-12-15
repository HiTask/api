HiTask API
====================

[HiTask](http://hitask.com) is an online task and project management service. With hiTask you can share tasks and projects with your team, add multi-user comments, track time, attach files, produce reports and much more.

This API allows you to build a hiTask client app or integrate hiTask with your infrastructure. API allows you to perform all the operations you can do in hiTask regularly.


JSON
-----------------

We only support JSON for serialization of data. Output format is data as root element.


Error handling
---------------

You need to check HTTP status in case there's an error. Basic rule is to check that code is not 200. If it's not 200 then expanded error code and error message will be in Json data.

When response statu is not 200 OK. The response contains Json date in format:
```json
{
 "error_message" : "This is an error message";
 "response_status" : 1;
}
```

Rate limiting
-------------

We only allow a certain number of requests per client per minute. If you exceed this limit you will have to wait before your next request is processed.


Authentication and security
--------------------------

This API is SSL/HTTPS only.

All methods require authentication. Authentication achieved through [User.authenticate](https://github.com/hitask/api/blob/master/documentation/user.md) which returns session id.
Your application have to provide the session id with every request. There are two ways of doing this:

* Cookie. If your application framework supports cookies automatically you don't have to do anything, cookie will be sent with every request.
* HTTP header parameter. Alternatively you can provide session id as "x-hi-session" header with every request.


API Access key
---------------

In order to provide you with access to API you need to obtain your API Key. API Key is a unique id assigned to you. To get the Key simply go into your account sttings page. We will ask you to provide the name of your integration/app.
You are required to provide your API Key when you authenticate: [User.authenticate](https://github.com/hitask/api/blob/master/documentation/user.md)


API endpoints
-----------------

* [User](https://github.com/hitask/api/blob/master/documentation/user.md)
* [Item (task, event, note, project)](https://github.com/hitask/api/blob/master/documentation/item.md)
* [Contact](https://github.com/hitask/api/blob/master/documentation/contact.md)
