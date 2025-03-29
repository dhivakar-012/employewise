Users
Retrieve a list of all users by using the /users endpoint.

Request
Terminal window
GET https://api.escuelajs.co/api/v1/users

Response
[
  {
    "id": 1,
    "email": "john@mail.com",
    "password": "changeme",
    "name": "Jhon",
    "role": "customer",
    "avatar": "https://i.imgur.com/LDOO4Qs.jpg"
  }
  // ... additional users
]

Get a Single User
Retrieve a specific user by providing the user’s id as a path parameter: /users/{id}

Request
Terminal window
GET https://api.escuelajs.co/api/v1/users/1

Response
{
  "id": 1,
  "email": "john@mail.com",
  "password": "changeme",
  "name": "Jhon",
  "role": "customer",
  "avatar": "https://i.imgur.com/LDOO4Qs.jpg"
}

Create a User
Create a new user by sending a POST request with the required user data to the /users/ endpoint.

Request
Terminal window
POST https://api.escuelajs.co/api/v1/users/

# Request Body
{
  "name": "Nicolas",
  "email": "nico@gmail.com",
  "password": "1234",
  "avatar": "https://picsum.photos/800"
}

Response
{
  "email": "nico@gmail.com",
  "password": "1234",
  "name": "Nicolas",
  "avatar": "https://i.imgur.com/yhW6Yw1.jpg",
  "role": "customer",
  "id": 24
}

Note: For demonstration purposes, passwords are stored as plain text. In a production environment, always implement proper password encryption.

Update a User
Update an existing user by sending a PUT request with the updated data and specifying the user’s id as a path parameter: /users/{id}

Request
Terminal window
PUT https://api.escuelajs.co/api/v1/users/1

# Request Body
{
  "email": "john@mail.com",
  "name": "Change name"
}

Response
{
  "id": 4,
  "email": "john@mail.com",
  "password": "1234",
  "name": "Change name",
  "role": "admin",
  "avatar": "https://i.imgur.com/yhW6Yw1.jpg"
}

Note: You only need to include the attributes you want to update in the request body. Other attributes will remain unchanged.

Check Email Availability
Verify if an email address is already registered in the system.

Request
Terminal window
POST https://api.escuelajs.co/api/v1/users/is-available

# Request Body
{
  "email": "john@mail.com"
}

Response
{
  "isAvailable": false
}
