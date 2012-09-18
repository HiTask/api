Item
========

Operations with items: tasks, projects, notes, files, etc.


Item  object properties
------------


* id: 12345, __global unique item id__
* guid: "123456abcdef", __global unique item id used for sharing__
* user_id: 12345, __user id of owner, user who created this item__
* title: "My Task",
* completed: false, 
* color: 0,   __color tag__
* category: 1,  __Category: 0:project 1: task 2:event 4: note 5:file__
* message: "Text", __item description text__
* parent: 0,  __unique id of parent item. 0 means item is not child of another item and not inside of project__
* recurring: 0, __0: not recurring, 1: daily, 2: weekly, 3: monthly, 4: yearly__
* assigneeId: 143465, __user id of user whom item is assigned to__
* participants: [ ], __array of user id for this item participants__
* time_last_update: "2012-07-15T19:55:00.000+10:00",
* time_create: "2012-01-25T14:58:51.000+11:00",
* start_date: "2012-03-15T19:00:00.000+10:00",
* is_all_day: false,
* shared: false,
* reminder_enabled: true,
* reminder_time: 5,
* reminder_time_type: "m",
* starred: false,
* time_track: false,  __flag to specify if time tracking is enabled fo rhtis item__
* time_est: 0,
* time_spent: 0,
* priority: 21000,  __Arbitrary priority. 10000-19999:low, 20000-29999:normal, 30000:high__
* tags: [ ],   __array or tags added to item_
* instances: [], __array of instances for recurring item__




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