# Tag


Operations with tags: add, remove, list tags


## 1. Get list of tags


* `GET 	/tag` will return list of tags

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

## 3. Update tag
------------

* `PUT    /tag/{id}`


## 4. Delete
------------

* `DELETE	/tag/{id}` 



