Jona's Crowdfunding Project - HobbyLobby

Purpose: To provide a platform where hoobies of all varieties can be funded by like-minded indivuduals. This will be done by interested hobbiest (project owner) posting projects (hoobies) they would like to pursue but have no funds to continue. Like-minded hobbiest (pledgers) can then donate to help sustain hobbies they have in common. This can range from mundane topics like baking to more nice interst like hammer-preservation.  

Future State: Platform to monetize hobbies and not just donations. 

Target audience: Anyone who wishes to support hobbies and having interest besides being corperate citizens
​
## Features
​
### User Accounts
​
- [X] Username
- [X] Email Address
- [X] Password
- First Name
- Last Name
​
### Project
​
- [X] Create a project
  - [X] Title
  - [X] Owner (a user)
  - [X] Description
  - [X] Image
  - [X] Target Amount to Fundraise
  - [X] Open/Close (Accepting new supporters)
  - [X] When was the project created
- [X] Ability to pledge to a project
  - [X] An amount
  - [X] The project the pledge is for
  - [X] The supporter
  - [X] Whether the pledge is anonymous
  - [] A comment to go with the pledge | Code under construction 
  
### Implement suitable update delete
​
**Note: Not all of these may be required for your project, if you have not included one of these please justify why.**
​
- Project
  - [X] Create
  - [X] Retrieve
  - [X] Update
  - [X] Destroy
- Pledge
  - [X] Create
  - [X] Retrieve
  - [ ] Update | Code under construction 
  - [ ] Destroy| Code under construction 
  
- User
  - [X] Create
  - [X] Retrieve
  - [X] Update
  - [X] Destroy
​
### Implement suitable permissions
​
**Note: Not all of these may be required for your project, if you have not included one of these please justify why.**
​
- Project
  - [X] Limit who can create |  ADDED ONLY SUPERUSER / ADMIN ONLY FOR PROJECTS / PERMISSIONS TO BE REFINED
  - [ ] Limit who can retrieve  | ALL CAN VIEW PROJECTS
  - [x] Limit who can update |  Code needs work - Ideal :  ONLY SUPERUSER / ADMIN ONLY FOR PROJECTS / PERMISSIONS TO BE REFINED
  - [ ] Limit who can delete|  Code needs work - Ideal :  ONLY SUPERUSER / ADMIN ONLY FOR PROJECTS / PERMISSIONS TO BE REFINED
- Pledge
  - [ ] Limit who can create |  Code needs work - Ideal :  ADDED ONLY SUPERUSER / ADMIN ONLY FOR PROJECTS / PERMISSIONS TO BE REFINED
  - [ ] Limit who can retrieve | Code needs work | NOT ADDED AS ALL CAN VIEW
  - [ ] Limit who can update |  Code needs work - Ideal :  ONLY SUPERUSER 
  - [ ] Limit who can delete |  Code needs work - Ideal :  ONLY SUPERUSER 
- Users
 - [ ]Limit who can retrieve | Code needs work 
 - [x]Limit who can update | Only User can update
 - [ ]Limit who can delete | NOT ADDED 
​
### Implement relevant status codes
​
- [x] Get returns 200
- [x] Create returns 201
- [x] Not found returns 404
​
### Handle failed requests gracefully 
​
- [x] 404 response returns JSON rather than text
​
### Use token authentication
​
- [X] impliment /api-token-auth/
​
## Additional features
​
- [ ] {Title Feature 1}
​
{{ description of feature 1 }}
​
- [ ] {Title Feature 2}
​
{{ description of feature 2 }}
​
- [ ] {Title Feature 3}
​
{{ description of feature 3 }}
​
### External libraries used
​
- [x] django-filter
​
​
## Part A Submission
​
- [x] A link to the deployed project - https://billowing-flower-9426.fly.dev/
- [x] A screenshot of Insomnia, demonstrating a successful GET method for any endpoint.
- [x] A screenshot of Insomnia, demonstrating a successful POST method for any endpoint.
- [x] A screenshot of Insomnia, demonstrating a token being returned.
- [x] Your refined API specification and Database Schema.
​
### Step by step instructions for how to register a new user and create a new project (i.e. endpoints and body data).
​
1. Create User
​
```shell
curl --request POST \
  --url http://127.0.0.1:8000/users/ \
  --header 'Content-Type: application/json' \
  --data '{
	"username": "testuser",
	"email": "not@myemail.com",
	"password": "not-my-password"
}'
```
​
2. Sign in User
​
```shell
curl --request POST \
  --url http://127.0.0.1:8000/api-token-auth/ \
  --header 'Content-Type: application/json' \
  --data '{
	"username": "testuser",
	"password": "not-my-password"
}'
```
​
3. Create Project
​
```shell
curl --request POST \
  --url http://127.0.0.1:8000/projects/ \
  --header 'Authorization: Token 5b8c82ec35c8e8cb1fac24f8eb6d480a367f322a' \
  --header 'Content-Type: application/json' \
  --data '{
	"title": "Donate a cat",
	"description": "Please help, we need a cat for she codes plus, our class lacks meows.",
	"goal": 1,
	"image": "https://upload.wikimedia.org/wikipedia/commons/c/c1/Dollar_bill_and_small_change.jpg",
	"is_open": true,
	"date_created": "2023-01-28T05:53:46.113Z"
}'
