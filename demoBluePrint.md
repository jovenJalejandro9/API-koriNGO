FORMAT: 1A

# KoriNGO

This is an App to make the management of the sponsorship cards of the NGO Koricancha (www.koricancha.org) easier. The App also will ease the visits of the volunteers who are goin to create or update one of these cards

# Group Users
Here is every resource related with the users

## User [/users/{user_id}]


+ Parameters
  + question_id: 1 (required, number) - ID of the User in form of an integer

+Attributes(object)
  + id_user: 1 (number, requiered)
  + name: Sonia (string,required)
  + first_surname: Lolo (string,required)
  + second_surname: Aria (string,required)
  + nickname: Sonya (string,required)
  + password: katuwira (password,required)
  + email: sonialolo@gmail.com: (email,required)
  + birthday: 1984-01-12 (date,required)
  + studies: ["journalism","psychology"] (array[string]) - Collection of the studies 
  + porfessions: ["teacher","psychologist"] (array[string]) - Collection of different professions
  + previous_volunteering: ["AMI3"] (array[string]) - Collection of different volunteering
  + published_at: 2016-03-05 (string, required) - An ISO8601 date when the user is created
  + rol: user (string,required) - Admin or user(normal user)

### View Users Detail [GET]
Retrieve a user with the given id

+ Response 200 (application/json)
    + Attributes (User)

## Users[/users{?limit}]
A resource representing all of my Users in the system.

+ Attributes(array[User])

### List All Users [GET]
Return a list of your users

+ Parameters
  + limit (number, optional) - The maximum number of results to return.

      A limit on the number of objects to be returned. Limit can range
      between 1 and the total size.

      + Default: '20'

+ Response 200 (application/json)
  + Attributes(Users)

### Create a User [POST]
Creates a new User.


\\Mirar ultimos datoss!! 
+ Attributes (object)
  + id_user: 1 (number, requiered)
  + name: Sonia (string,required)
  + first_surname: Lolo (string,required)
  + second_surname: Aria (string,required)
  + nickname: Sonya (string,required)
  + password: katuwira (password,required)
  + email: sonialolo@gmail.com: (email,required)
  + birthday: 1984-01-12 (date,required)
  + studies: ["journalism","psychology"] (array[string]) - Collection of the studies 
  + porfessions: ["teacher","psychologist"] (array[string]) - Collection of different professions
  + previous_volunteering: ["AMI3"] (array[string]) - Collection of different volunteering
  + rol: user (string,required) - Admin or user(normal user)

+ Request (application/json)
  + Headers
    + Authentication: <user_token>
+ Response 200 (application/json)
  + Attributes (User)


## Update a user [PUT]
Update infromation of some user
+ Request (application/json)
  + Attributes (User)
+ Response 200 (application/json)
  + Attributes (User)


## Delete a user [POST]
//Borra todo el recursoo????
## Login user [POST]
//hay que hacerlo??


# Personal Information[/]

{
  "name": "Carlos",
  "first_surname": "Vilchez",
  "second_surname": "Orlandini",
  "status": {
              "nickname_name": "Sonya",
              "education": [
                {
                  "id_education_center": 12321,
                  "education_center": "katuwira"
                },{
                  "id_education_center": 12321,
                  "education_center": "katuwira"
                }
              ]
            }
}
# status[cards]

{
  "nickname_name": "Sonya",
  "education": [
    {
      "id_education_center": 12321,
      "education_center": "katuwira"
    }
  ]
}

## Sheet [/Sheets/{sheet_id}]
// Ver bien como gestionar el la parte del status. Las estructuras son diferentes
// Mirar como van las fotos
+ Parameters
  + question_id: 1 (required, number) - ID of the thecnical sheet

+Attributes(object)
  + id_sheet: 1 (number, requiered)
  + name: Carlos (string,required)
  + first_surname: Vilchez (string,required)
  + second_surname: Orlandini (string,required)
  + bthday: 1993/04/21
  + dni: 702076478x (string,required)
  + zone: Chiclayo (string,required)
  + address: Pueblo Joven 4 de Noviembre 23, Chiclayo: (email,required)
  + family_photos: [<url1>,<url2>] (array[string]) - Collection of the family Photo urls
  + house_photos: [<url1>,<url2>] (array[string]) - Collection of the house Photo urls
  + responsible_name: (array(Status)) - Array of status Object
    [
      {
        nombre: Rita, 
        parentesco: Madre, 
        DNI: 71182993C, 
        tel: 722718290
      }
    ]
  + family_information(array(array(Status))) - Array of array of Status Object    
    [
      [
        {
          name: Rita,
          first_surname: Orlandini,
          second_surname : Ruiz,
          bthday: 2016-12-03
        }
      ]
    ]
  + center: array(Status) - centro actual, anterior, annio de entrada
    [
      {
        prev_name, 
        current_name,
        timestamp
      }
    ]
  + special_help: array(Status)
  [
    {
      help_name,
      center_name,
      timestamp,
      asistance,
      coment
    }
  ] 

  + free_time (array(Status))
    [
      {
        activities: [array],
        close_people: [array]
        env_realation,

      }
    ]
  + medical_situation (array(Status))
    [
      {
        diagnostic: [],
        movility,
        chair,
        comunication,
        done_test,

      }
    ]

  + dni: 702076478x (string,required)
  + zone: Chiclayo (string,required)
  + birthday: 1984-01-12 (date,required)
  + studies: ["journalism","psychology"] (array[string]) - Collection of the studies 
  + porfessions: ["teacher","psychologist"] (array[string]) - Collection of different professions
  + previous_volunteering: ["AMI3"] (array[string]) - Collection of different volunteering
  + published_at: 2016-03-05 (string, required) - An ISO8601 date when the user is created
  + rol: user (string,required) - Admin or user(normal user)



