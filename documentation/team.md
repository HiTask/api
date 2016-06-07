Team
========

Team members and team properties


1. Invite to join team account
------------

* `POST 	/team/member` 

### Parameters

Parameter | Type | Description
------------ | ------------- | ------------
email | string | Valid email address. **Required**


### Response codes

HTTP code | API Error code | Description
------------ | ------------- | ------------
200 |  | Invited,added
400 | 5 | bad request, email address invalid
412 | 16 | Already a member, (this email address is already member of Team)
400 | 12 | User licenses exceeded

