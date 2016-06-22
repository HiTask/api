# Team

Team members and team properties

## 1. Get list of team members

* `GET /team`

## 2. Invite to join team account

* `POST 	/team/member` 

### Parameters

Parameter | Type | Description
------------ | ------------- | ------------
email | string | Valid email address. **Required**
name | string | Full name. First name and last name separated by space. e.g. "Firstname Lastname"

### Response codes

HTTP code | API Error code | Description
------------ | ------------- | ------------
200 |  | Invited,added
400 | 5 | bad request, email address invalid
412 | 16 | Already a member, (this email address is already member of Team)
412 | 79 | User already invited in this team
400 | 12 | User licenses exceeded


## 3. Remove team member

Removes team member or invited user

* `DELETE /team/member`

### Parameters

Parameter | Type | Description
------------ | ------------- | ------------
id | integer | member user id

### Response codes

HTTP code | API Error code | Description
------------ | ------------- | ------------
200 |  | member removed
404 | 1 | member not found
400 | 4 | "id" parameter is mandatory

## 4. Resend invitation

In case user did not receive email invitation use this method to re-send invitation again

* `POST /team/member/resend`

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
