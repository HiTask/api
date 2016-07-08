# Tag


Operations with tags: add, remove, list tags


## 1. Get list of tags


* `GET 	/tag` will return list of tags

### Mandatory params:
Param | Type | Description
------------ | ------------- | ------------
<code>session_id</code>| text | User session.

### Example response

```js
[{"name":"privatetag","shared":false,"id":388730},{"name":"tag","shared":true,"id":388728},{"name":"тег","shared":true,"id":388729}]
```

### Response fields:
Field | Type | Description
------------ | ------------- | ------------
<code>id</code>| long | Globally unique primary identifier for a tag.
<code>name</code>| text | Name of the tag.
<code>shared</shared> | boolean | Indicates if tag linked to shared item or private item for current user.


### Response codes

HTTP code | API Error code | Description
------------ | ------------- | ------------
200 |  | Returns array of tags.
400 | 4 | API session is required.


## 2. Add tag
------------

* `POST	/tag`

### Mandatory params:
Param | Type | Description
------------ | ------------- | ------------
<code>session_id</code>| text | User session.
<code>name</code>| text | Name of the new tag.
<code>item_id</code>| long | Identifer of item.

### Example response

```js
{"name":"new tag from api","shared":false,"id":388731}
```

### Response fields:
Field | Type | Description
------------ | ------------- | ------------
<code>id</code>| long | Globally unique primary identifier for a tag.
<code>name</code>| text | Name of the tag.
<code>shared</shared> | boolean | Indicates if tag linked to shared item or private item for current user.


### Response codes

HTTP code | API Error code | Description
------------ | ------------- | ------------
200 |  | Returns created tag.
400 | 4 | Tag name is required.
400 | 4 | Item ID is required.
404 | 1 | Item not found.
403 | 3 | No enough permissions to modify item.

## 3. Update tag
------------

* `PUT    /tag/{id}`

### Mandatory params:
Param | Type | Description
------------ | ------------- | ------------
<code>session_id</code>| text | User session.
<code>name</code>| text | New name of the tag.
<code>id</code>| long | Identifer of tag (param is part of the URL).

### Example response

```js
{"name":"update tag from api","shared":false,"id":388731}
```

### Response fields:
Field | Type | Description
------------ | ------------- | ------------
<code>id</code>| long | Globally unique primary identifier for a tag.
<code>name</code>| text | Name of the tag.
<code>shared</shared> | boolean | Indicates if tag linked to shared item or private item for current user.


### Response codes

HTTP code | API Error code | Description
------------ | ------------- | ------------
200 |  | Returns updated tag.
400 | 4 | Tag name is required.
404 | 1 | Tag not found.
403 | 3 | No enough permissions to modify tag because no enough permissions to modify respective item.

## 4. Delete
------------

* `DELETE	/tag/{id}` 

### Mandatory params:
Param | Type | Description
------------ | ------------- | ------------
<code>id</code>| long | Identifer of tag (param is part of the URL).

### Example response

```js
{"response_status":0}
```

### Response codes

HTTP code | API Error code | Description
------------ | ------------- | ------------
200 |  | Tag deleted.
404 | 1 | Tag not found.
403 | 3 | No enough permissions to delete shared tag.

