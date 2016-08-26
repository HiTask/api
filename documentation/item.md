# Item

Operations with items: tasks, events, projects, notes, files.


## Item  object properties


<table>
    <tr>
        <th>Field</th>
        <th>Type</th>
         <th>Example</th>
        <th>Description</th>
    </tr>
    <tr>
        <td><code>id</code></td>
        <td>long</td>
        <td>123000</td>
        <td>Globally unique item Identifier</td>
    </tr>
       <tr>
        <td><code>guid</code></td>
        <td>String (UDID)</td>
        <td>123456abcdef</td>
        <td>Globally unique item Identifier used for public sharing</td>
    </tr>
     <tr>
        <td><code>user_id</code></td>
        <td>long</td>
        <td>123000</td>
        <td>user id of owner, user who created this item</td>
    </tr>  
     <tr>
        <td><code>title</code></td>
        <td>String (512)</td>
        <td>My Task</td>
        <td>title</td>
    </tr>  
       <tr>
        <td><code>completed</code></td>
        <td>int</td>
        <td>0</td>
        <td>Indication if this item is completed</td>
    </tr>  
       <tr>
        <td><code>color</code></td>
        <td>int</td>
        <td>0</td>
        <td>Color tag (index of predefined colors) used for items (tasks, events, notes, ..). Onde of these colors: [no color, '#FB7E6E', '#F8B957', '#F3DF5B', '#C2D95B', '#6CB4FF', '#CAA4DF', '#B8B8B8']</td>
    </tr> 
    <tr>
        <td><code>color_value</code></td>
        <td>Strng</td>
        <td>#5e93c3</td>
        <td>Color value used for projects. Default: #5e93c3<br/>One of these colors: ['#5e93c3', '#fc2f6a', '#fd9426', '#fecb2e', '#55ce2e', '#cb77df', '#a18460']</td>
    </tr> 
    <tr>
        <td><code>category</code></td>
        <td>int</td>
        <td>1</td>
        <td>Category (or type) of item: 0:project 1: task 2:event 4: note 5:file</td>
    </tr> 
       <tr>
        <td><code>message</code></td>
        <td>String (5000)</td>
        <td>Hello</td>
        <td>Item description text</td>
    </tr> 
       <tr>
        <td><code>parent</code></td>
        <td>long</td>
        <td>0</td>
        <td>Unique id of parent item. Default: 0. 0 means item is not child of another item and not inside of project</td>
    </tr> 
       <tr>
        <td><code>recurring</code></td>
        <td>int</td>
        <td>0</td>
        <td>0: not recurring, 1: daily, 2: weekly, 3: monthly, 4: yearly</td>
    </tr> 
       <tr>
        <td><code>assigneeId</code></td>
        <td>long</td>
        <td>0</td>
        <td>Assignee, primary responsible person. User id of user whom item is assigned to</td>
    </tr> 
        <tr>
        <td><code>participants</code></td>
        <td>comma separated list of user identifiers</td>
        <td>322,413</td>
        <td>array of user id for this item participants</td>
    </tr>    
         <tr>
        <td><code>start_date</code></td>
        <td>Date</td>
        <td>2012-03-15T19:00:00.000+10:00</td>
        <td>Start date and time for this item. Default:null.</td>
    </tr>    
          <tr>
        <td><code>end_date</code></td>
        <td>Date</td>
        <td>2012-03-15T19:00:00.000+10:00</td>
        <td>End date and time for this item. Default:null.</td>
    </tr>
             <tr>
        <td><code>is_all_day</code></td>
        <td>int</td>
        <td>0</td>
        <td>Indicator that this item is "all day" event. Only date without time should be used from start/end date field..</td>
    </tr>
    <tr>
        <td><code>alerts</code></td>
        <td>JSON array</td>
        <td>0</td>
        <td>
            Create/Update/Delete reminders:<br />
            <code>[{"timeType":4,"time":0,"timeSpecified":null,"repeat":0,"repeatInterval":0,"sound":true,"alert":true,"email":true,"push":true},{"timeType":4,"time":5,"timeSpecified":null,"repeat":0,"repeatInterval":0,"sound":true,"alert":true,"email":true,"push":true},{"timeType":3,"time":1,"timeSpecified":null,"repeat":0,"repeatInterval":0,"sound":true,"alert":true,"email":true,"push":true},{"timeType":1,"time":0,"timeSpecified":"2016-08-31T11:00:00.000+04:00","repeat":0,"repeatInterval":0,"sound":true,"alert":true,"email":true,"push":true}]</code>
        </td>
    </tr>    
    <tr>
        <td><code>shared</code></td>
        <td>int</td>
        <td>0</td>
        <td>0: Item is private. 1: item is shared, visile to team memebrs (Business account feature)</td>
    </tr>
   <tr>
        <td><code>time_last_update</code></td>
        <td>Date</td>
        <td>2012-03-15T19:00:00.000+10:00</td>
        <td>Timestamp when this item was last changed (updated).</td>
    </tr>
       <tr>
        <td><code>time_create</code></td>
        <td>Date</td>
        <td>2012-03-15T19:00:00.000+10:00</td>
        <td>Timestamp when this item was created.</td>
    </tr>
           <tr>
        <td><code>starred</code></td>
        <td>int</td>
        <td>0</td>
        <td>If item is marked as starred, 1 or 0</td>
    </tr>
           <tr>
        <td><code>time_track</code></td>
        <td>int</td>
        <td>0</td>
        <td>1/0 flag to specify if time tracking is enabled for htis item. Default:0.</td>
    </tr>
               <tr>
        <td><code>time_est</code></td>
        <td>float</td>
        <td>0</td>
        <td>Time estimated for this item, in hours. Used in time tracking calculations.Optional.</td>
    </tr>
                 <tr>
        <td><code>time_spent</code></td>
        <td>float</td>
        <td>0</td>
        <td>Total time spent recorded for this item.</td>
    </tr>
                     <tr>
        <td><code>priority</code></td>
        <td>int</td>
        <td>20000</td>
        <td>Arbitrary priority. 10000-19999:low, 20000-29999:normal, 30000:high. Default: 20000 (normal)</td>
    </tr>
                        <tr>
        <td><code>tags</code></td>
        <td>comma separated list of tags</td>
        <td>"work","home"</td>
        <td>array or tags added to item</td>
    </tr>
     <tr>
        <td><code>instances</code></td>
        <td>array[item_instance]</td>
        <td>[]</td>
        <td>array of instances for recurring item. at PUT/POST requests this field is ignored by the server.</td>
    </tr>
    <tr>
        <td><code>location</code></td>
        <td>object</td>
        <td>{"longitude":123.1234567,"latitude":-4.0987654321,"address":"qwe"}</td>
        <td>Map that contains long/lat coordinates and address</td>
    </tr>
</table>

# Methods 

## 1 Get array of items


* `GET    /item` 

This method will return array of all items: tasks, events, files including projects


### 1.2 Get delta update of items

* `GET  	/item/since/{timestamp}`

Returns list of items that were changed or added since specified date


## 2 Create item

* `POST    /item` will create new item


## 3 Update

* `PUT    /item` will update (modify) item

### Response codes for Create and Update

HTTP code | API Error code | Description
------------ | ------------- | ------------
200 |  | Created/updated
400 | 73 | Unable to add {principal X} because project/parent item is not shared with {principal X}.
400 | 74 | {principal X} permission can not be {modified/added/removed} because it will conflict with parent {permission X} permissions.
400 | 75 | {user X} can not be {assignee/participant} because they don't have access to project {project name}.
400 | 76 | Owner {owner name} is not allowed to change own permission.
400 | 77 | Permission {principal X} downgrade to {permission X} is not allowed because parent has {permission Y} for this principal.
400 | 78 | Cannot remove {assignee/participant} {user name} permission.


## 4 Delete

* `DELETE    /item/{id}` will delete item

Parameters:
* {id}: unique id of item.

User performing delete request must have sufficient rights to delete this object

Possible HTTP return responses:

* 200 operation successful
* 404 item not found. It may be already deleted or not visible to current user.
* 403 not authorised

## 5 History

### 5.1 Retrieve item history including comments:

* `GET    /item/history?id={item id}` 

### 5.2 Add comment

* `POST    /item/comment` will add a new comment to the item

Parameters: id: item id, message: comment body text

### 5.3 Delete comment

* `DELETE    /item/comment` will delete comment
