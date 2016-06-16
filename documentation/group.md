Groups
========

Operations with user groups. Organize team and contacts into groups.


Get list of groups
------------

* `GET 	/groups` will return list of user's groups and contacts

### Example response

```js
[
{
id: "q9xsalg4tc7hrbaddh56fxg1ekuqrci39g8i2y7krmwa2qny8s5",
name: "Everyone",
code: "EVERYONE",
color: "#FFFFFF",
members: [
1866247,
1861630,
1866033,
1286619
],
type: 1
}
]
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
     <tr>
        <td><code>name</code></td>
        <td>String</td>
        <td>Group name</td>
    </tr>
     <tr>
        <td><code>type</code></td>
        <td>int</td>
        <td>Group special type. If =1 then this is "Everyone" group containing all team members.</td>
    </tr>
</table>




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
