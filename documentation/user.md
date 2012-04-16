User
========

Operations related to current user's account: authenticate, sign up, etc.


Authenticate
------------

* `GET /user/authenticate` will authenticate user usign user name and password


Validate signup information
------------

This method is used to validate user registration (sign up ) form before submitting

* `GET /user/validatesignup` will verify that user name is not taken, and other parameters are valig


Sign out
------------

* `GET /user/signout` Close user's session.




