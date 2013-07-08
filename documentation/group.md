Groups
========

Operations with user groups. Organize team and contacts into groups.


Get list of groups
------------

* `GET 	/group` will return list of user's groups and contacts

### Example response

```js
{

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
        <td>Globally unique primary identifier </td>
    </tr>
 
</table>



Add tag
------------

* `POST	/tag`


Add Group
--------------

* `POST /group`

Only user level Administrator can create group

parameters: 

* name: group name


Update group
---------------

* `PUT /group`

Update group. Only user level Administrator can update group

parameters: 

* id
* name: group name
* code
* color

Delete Group
---------------

* `DELETE /group`

Only user level Administrator can create group.
This *does not delete contacts*. only group is deleted.

parameter:

* group id


Add Contact to Group
---------------------

* `POST /group/{groupId}/contact{id}`

Add contact to the group

Only user level Administrator can add contact to the group

Remove Contact from a Group
--------------------

* `DELETE /group/{groupId}/contact{id}`

Remove contact form the group

Only user level Administrator can add remove contact form the group.
