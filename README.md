About hiTask
====================

[HiTask](http://hitask.com) is an online task and project management service. With hiTask you can share tasks and projects with your team, add multi-user comments, track time, attach files, produce reports and much more.

hiTask API
----- 

API is public and is available to everyone.
This API allows you to build a hiTask client app or integrate hiTask with your infrastructure. API allows you to perform all the operations you can do in hiTask regularly.

* **RESTful.** API is designed in accordance with [REST](http://en.wikipedia.org/wiki/Representational_state_transfer) patterns and is so called RESTful API.
* **JSON.** We only support JSON for serialization of data. Response data is returned as root element.

API Access key
---------------

To access the API you need to have API Key. API Key is a unique identifier assigned to you. To get your Key simply go into your hiTask account settings page. You  will be asked to provide the name of your integration/app.
You are required to provide your API Key as a parameter for some methods, for example API Key is required when you authenticate user session: [User.authenticate](https://github.com/hitask/api/blob/master/documentation/user.md)


API Endpoint URL
---------------

API endpoint is `https://hitask.com/api/{method}` where {method} is the name of API method. 


Authentication and security
--------------------------

This API is SSL/HTTPS only.

All methods require authentication. Authentication achieved through [User.authenticate](https://github.com/hitask/api/blob/master/documentation/user.md) which returns session id.
Your application have to provide the session id with every request. There are two ways of doing this:

* Cookie. If your application framework supports cookies automatically you don't have to do anything, cookie will be sent with every request.
* HTTP header parameter. Alternatively you can provide session id as "x-hi-session" header with every request.

### Rate limiting

We only allow a certain number of requests per client per minute. If you exceed this limit you will have to wait before your next request is processed.


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


API methods
-----------------

* [User:](https://github.com/hitask/api/blob/master/documentation/user.md) authenticate, get user account information
* [Item:](https://github.com/hitask/api/blob/master/documentation/item.md) task, event, note, project objects
* [Contact:](https://github.com/hitask/api/blob/master/documentation/contact.md) information about contacts
* Tag: list tags, add, delete, update tags

