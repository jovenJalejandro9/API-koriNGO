FORMAT: 1A

# KoriNGO

This is an App to make the management of the sponsorship cards of the NGO Koricancha (www.koricancha.org) easier. The App also will ease the visits of the volunteers who are goin to create or update one of these cards


# User [/users/{user_id}]

A User object has the following attributes:

    + name
    + first_surname
    + second_surname
    + nickname
    + password
    + email
    + birthday
    + studies - Collection of the studies
    + porfession  - Collection of different professions
    + previous_volunteering - Collection of different volunteering
    + published_at - An ISO8601 date when the user is created
    + rol - Admin or user(normal user)
//    + url

+ Parameters
    + question_id: 1 (required, number) - ID of the User in form of an integer

## View Users Detail [GET]

+ Response 200 (application/json)

  {
    "name": "Sonia",
    "first_surname": "Lolo"
    "second_surname": "Aira"
    "nickname": "Sonya"
//    "password": "katuwira"
    "email": "soniaLolo@gmail.com"
    "birthday": "1984-01-12"
    "studies": ["social work"]
    "professions" : ["teacher", "psychologist"]
    "previous_volunteering": "AMI3"
    "published_at": "2018-11-11T08:40:51.620Z",
 //   "url": "/questions/1",
    "rol": "admin"
  }

//que es la page??
# Users Collection [/users{?page}]

// Ver si hace falta hacer la coleccion 
+ Parameters
    + page: 1 (optional, number) - The page of questions to return


## List All Users [GET]
//Que son los headers del 
+ Response 200 (application/json)
  + Headers
    Link: </questions?page=2>; rel="next"
  + Body
    [
      {
        "name": "Sonia",
        "first_surname": "Lolo"
        "second_surname": "Aira"
        "nickname": "Sonya"
    //    "password": "katuwira"
        "email": "soniaLolo@gmail.com"
        "birthday": "1984-01-12"
        "studies": ["social work"]
        "professions" : ["teacher", "psychologist"]
        "previous_volunteering": "AMI3"
        "published_at": "2018-11-11T08:40:51.620Z",
        "url": "/questions/1",
        "rol": "admin"
      }
    ]


## Create a new user [POST]
You may create a new user. It takes a JSON object.

    + name (string)
    + first_surname (string)
    + second_surname (string)
    + nickname (string)
//    + password 
    + email (string)
    + birthday (date)
    + studies (array[string]) - Collection of the studies 
    + porfession (array[string])- Collection of different professions
    + previous_volunteering (array[string])- Collection of different volunteering
    + rol (string) - Admin or user(normal user)

+ Request (application/json)

  {
    "name": "Sonia",
    "first_surname": "Lolo"
    "second_surname": "Aira"
    "nickname": "Sonya"
//    "password": "katuwira"
    "email": "soniaLolo@gmail.com"
    "birthday": "1984-01-12"
    "studies": ["social work"]
    "professions" : ["teacher", "psychologist"]
    "previous_volunteering": "AMI3"
//    "url": "/questions/1",
    "rol": "admin"
  }


+ Response 201 (application/json)

  + Headers

    Location: /questions/2

  + Body

    {
      "name": "Sonia",
      "first_surname": "Lolo"
      "second_surname": "Aira"
      "nickname": "Sonya"
  //    "password": "katuwira"
      "email": "soniaLolo@gmail.com"
      "birthday": "1984-01-12"
      "studies": ["social work"]
      "professions" : ["teacher", "psychologist"]
      "previous_volunteering": "AMI3"
      "published_at": "2018-11-11T08:40:51.620Z",
      "url": "/questions/1",
      "rol": "admin"
    }


## Modify a user [POST]
## Delete a user [POST]
//Borra todo el recursoo????
## Login user [POST]
//hay que hacerlo??


# Personal Information[cards]

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





## Choice [/questions/{question_id}/choices/{choice_id}]

+ Parameters
    + question_id: 1 (required, number) - ID of the Question in form of an integer
    + choice_id: 1 (required, number) - ID of the Choice in form of an integer

### Vote on a Choice [POST]

This action allows you to vote on a question's choice.

+ Response 201

    + Headers

            Location: /questions/1

## Questions Collection [/questions{?page}]

+ Parameters
    + page: 1 (optional, number) - The page of questions to return

### List All Questions [GET]

+ Response 200 (application/json)

    + Headers

            Link: </questions?page=2>; rel="next"

    + Body

            [
                {
                    "question": "Favourite programming language?",
                    "published_at": "2014-11-11T08:40:51.620Z",
                    "url": "/questions/1",
                    "choices": [
                        {
                            "choice": "Swift",
                            "url": "/questions/1/choices/1",
                            "votes": 2048
                        }, {
                            "choice": "Python",
                            "url": "/questions/1/choices/2",
                            "votes": 1024
                        }, {
                            "choice": "Objective-C",
                            "url": "/questions/1/choices/3",
                            "votes": 512
                        }, {
                            "choice": "Ruby",
                            "url": "/questions/1/choices/4",
                            "votes": 256
                        }
                    ]
                }
            ]

### Create a New Question [POST]

You may create your own question using this action. It takes a JSON object containing a question and a collection of answers in the form of choices.

+ question (string) - The question
+ choices (array[string]) - A collection of choices.

+ Request (application/json)

        {
            "question": "Favourite programming language?",
            "choices": [
                "Swift",
                "Python",
                "Objective-C",
                "Ruby"
            ]
        }

