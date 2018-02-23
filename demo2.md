FORMAT: 1A

# KoriNGO

//Meter headers!! 

This is an App to make the management of the sponsorship cards of the NGO Koricancha (www.koricancha.org) easier. The App also will ease the visits of the volunteers who are goin to create or update one of these cards

# Group Users
Here is every resource related with the users

## User [/users/{user_id}]

+ Parameters
  + user_id: 1 (required, number) - ID of the User in form of an integer

+ Attributes(object)
  + id_user: 1 (number, required)
  + name: "Sonia" (string,required)
  + first_surname: Lolo (string,required)
  + second_surname: Aria (string,required)
  + nickname: Sonya (string,required)
  + password: katuwira (string,required)
  + email: sonialolo@gmail.com: (string,required)
  + birthday: 1984-01-12 (date,required)
  + studies: ["journalism","psychology"] (array[string]) - Collection of the studies 
  + porfessions: ["teacher","psychologist"] (array[string]) - Collection of different professions
  + previous_volunteering: ["AMI3"] (array[string]) - Collection of different volunteering
  + published_at: 2016-03-05 (string, required) - An ISO8601 date when the user is created
  + rol: user (string,required) - Admin or user(normal user)

### View Users Detail [GET]
Retrieve a user with the given id

+ Response 201 (application/json)
    + Attributes (User)

## Users [/users{?limit}]
A resource representing all of my Users in the system.

+ Attributes(array[User])

### List All Users [GET]
Return a list of your users

+ Parameters
  + limit (number, optional) - The maximum number of results to return.

      A limit on the number of objects to be returned. Limit can range
      between 1 and the total size.

      + Default: '20'

+ Response 201 (application/json)
  + Attributes(array[Users])

### Create a User [POST]
Creates a new User.


+ Attributes (object)
  + id_user: 1 (number, required)
  + name: Sonia (string,required)
  + first_surname: Lolo (string,required)
  + second_surname: Aria (string,required)
  + nickname: Sonya (string,required)
  + password: katuwira (string,required)
  + email: sonialolo@gmail.com: (string,required)
  + birthday: 1984-01-12 (date,required)
  + studies: journalism,psychology (array[string]) - Collection of the studies 
  + porfessions: teacher,psychologist (array[string]) - Collection of different professions
  + previous_volunteering: AMI3 (array[string]) - Collection of different volunteering
  + rol: user (string,required) - Admin or user(normal user)

+ Request (application/json)

+ Response 200 (application/json)
  + Attributes (User)

### Update a user [PUT]
Update infromation of some user
+ Request (application/json)
  + Attributes (User)
+ Response 200 (application/json)
  + Attributes (User)


### Delete a user [POST]
Update infromation of some user
+ Request (application/json)
  + Attributes (User)
+ Response 200 (application/json)
  + Attributes (User)
  
### Login user [POST]
Update infromation of some user
+ Request (application/json)
  + Attributes (User)
+ Response 200 (application/json)
  + Attributes (User)



