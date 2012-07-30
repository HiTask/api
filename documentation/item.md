Item
========

Operations with items: tasks, projects, notes, files, etc.

Get array of items
------------

* `GET    /item` 

This method will return array of all items: tasks, events, files including projects


Get delta update of items
------------

* `GET  	/item/since/{timestamp}`

Returns list of items that were changed or added since specified date


Create
------------

* `POST    /item` will create new item



Update
------------

* `PUT    /item` will update (modify) item


Delete
------------

* `DELETE    /item/{id}` will delete item

Parameters:
* {id}: unique id of item.

User performing delete request must have sufficient rights to delete this object

Possible HTTP return responses:

* 200 operation successful
* 404 item not found. It may be already deleted or not visible to current user.
* 403 not authorised

Add comment
------------

* `POST    /item/comment` will add a new comment to the item


Delete comment
------------

* `DELETE    /item/comment` will delete comment