##modules needed
- knex
- cookie-parser
- cookie-session
- morgan
- locus
- express
- bcrypt
- express-session

#signup `/signup`
- validation:
	1. email: use HTML5 validation, make case insensitive
	2. password: minimum length of 6? --> error: password must be at least 6 characters
	3. password: two fields match --> error: passwords do not match
- HTTP POST
	1. test to see if existing user --> error: user already exists
	2. hash password
	3. add new user to database
- signin the new user
- send to (logged in) `/dashboard` page

#signin `/`
- validation:
	1. email: use HTML5 validation --> error: invalid email address
	2. password: length --> error
- HTTP POST
	1. check db for email --> error: (not found)
	2. hash password
	3. check hash with user's hash in db --> error: (invalud password)
	4. set session/cookie stuff (????)
- send to `/dashboard` page

#signout
- clear session/cookie
- send to `/` signin page

#database
- primary key (and userId)
- email string
- password hash (with salt using bcrypt)