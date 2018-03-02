FORMAT: 1A

# KoriNGO

This is an App to make the management of the sponsorship cards of the NGO Koricancha (www.koricancha.org) easier. The App also will ease the visits of the volunteers who are goin to create or update one of these cards

# Data Structures

## UserStruct
  + id: 1 (number, required) - ID of the user
  + name: Sonia (string,required) - Name of the user
  + first_surname: Lolo (string,required) - First surname of the user
  + second_surname: Aria (string,required) - Second surname of the user
  + nickname: Sonya (string,required) - Nickname user. Used on the login(or email)
  + email: sonialolo@gmail.com: (string,required) - User email. Used on the login (or Nickname)
  + birthday: 1984-01-12 (string,required) - User bithday
  + studies: journalism,psychology (array[string],required) - Collection of the studies. If the usuer did not study anything the collection will be empty
  + porfessions: teacher,psychologist (array[string],required) - Collection of different professions. If the usuer did not work anything the collection will be empty
  + prev_volunteering: AMI3 (array[string],required) - Collection of different volunteering. If the usuer did not study anything the collection will be empty
  + created_at: Wed Feb 28 2018 17:02:43 GMT+0100(string, required) - An ISO8601 date when the user is created
  + updated: Wed Feb 28 2018 17:02:43 GMT+0100 (string, required) - An ISO8601 date when the user is created
  + rol: user (string,required) - Admin or user(normal user)

## UsersStruct (array)
+ (UserStruct)

## VisitStructure
  + id: 1(number,required) - Visit Id
  + sheet_id: 1(number,required) - Sheet Id
  + user_id: 1(number,required) - Id of user who is goint to do or update the sheet  
  + date: 2018/04/04 (string, required) - Date when the visit is done
  + state: pendient(string,required) - State of the visit(pendient, incomplete, done) 

## VisitsStructure(array)
  + (VisitStructure)

## StateStruct
  + id: 4(number,required) - Id of the current state
  + prev_state: 3(number, required) - Id of the previous value
  + value (required) - Any kind of variable
    + diagnsose: Autism(string,required) - Disagnose
    + start_year: 1993(number,required) - Diagnoise year 
  + timestamp:  Wed Feb 28 2018 17:02:43 GMT+0100(string,required) - Date of record data
  + user_id: 3(number, required) - Id of the user who modify the field

## StatesStruct(array)
  + (StateStruct)

## SheetStruct 
  + id: 1 (number, required) - Sheet ID
  + name: Carlos (string,required) - Name of the participant
  + first_surname: Vilchez (string,required) - Participant first surname
  + second_surname: Orlandini (string) - Participant second surname
  + bthday: 1993/04/21 (string) - Participant birthday
  + dni: 702076478x (string) - Participant DNI
  + zone: Chiclayo (string,required) - Zona where the participant is living
  + address: Pueblo Joven 4 de Noviembre 23, Chiclayo (string,required) - Participant address

  + family_fotos:<url1>,<url2> (array[State]) - List of State Object
  + house_photos:<url1>,<url2>  (array[State]) - Array of State Object
  + responsible (array[State]) - Array of State object
  + family_information (array[State]) - Array of State object  
  + center (array[State]) - Array of Status Object. School
  + therapies(array[State]) - Array of State object  
  + social_situation (array[State]) - Array of State object  
  + medical_info (array[State]) - Array of State object 
  + home_info (array[State]) - Array of State object 
  + economic_info (array[State]) - Array of State object 
  + general_information (array[State]) - Array of State object 
  + manifested_information (array[State]) - Array of State object 
  + detected_information (array[State]) - Array of State object 
  + warning_information (array[State]) - Array of State object 
  + complete: false (boolean, required) - false if the sheet requires further attention to fill the information

## SheetsStructure(array)
  + (SheetStruct)



# Group Users
Here is every resource related with the users

## User [/users/{user_id}]
Users are the people who can acces to our system. Every user have these fields:

name | example_value | kind_value | requiered | description
--:| ---- | --- | --- | --- 
id | 1 |number|required| ID of the user
name|Sonia |string|true| Name of the user
first_surname| Lolo |string|true|First surname of the user
second_surname| Aria |string|true| Second surname of the user
nickname|Sonya |string|true|Nickname user. Used on the login(or email)
email| sonialolo@gmail.com|string|true|User email. Used on the login (or Nickname)
birthday| 1984-01-12 |string|true| User bithday
studies|journalism,psychology|array[string]|true| Collection of the studies. If the usuer did not study anything the collection will be empty
porfessions|teacher,psychologist |array[string]|true| Collection of different professions. If the usuer did not work anything the collection will be empty
prev_volunteering| AMI3 |(array[string]|true|Collection of different volunteering. If the usuer did not study anything the collection will be empty
created_at| Wed Feb 28 2018 17:02:43 GMT+0100|string| true| An ISO8601 date when the user is created
updated|Wed Feb 28 2018 17:02:43 GMT+0100 |string| true| An ISO8601 date when the user is created

+ Attributes(UserStruct)

+ Parameters
  + user_id: 1 (required, number) - ID of the User in form of an integer

+ Model (application/json)

    JSON representation of User Resource.

    + Headers

            Authentication: <user_token> - To have acces to this resource the user has to be identified 

    + Body

            {
              "id": 1,
              "name": "Sonia",
              "first_surname": "Lolo",
              "second_surname": "Aria",
              "nickname": "Sonya",
              "email": "sonialolo@gmail.com:",
              "birthday": "1984-01-12",
              "studies": [
                "journalism",
                "psychology"
              ],
              "porfessions": [
                "teacher",
                "psychologist"
              ],
              "prev_volunteering": [
                "AMI3"
              ],
              "published_at": "2016",
              "rol": "user"
            }

### View User Details [GET]

Retrieve a User with the given id in the paremeters

+ Params
  + user_id: 1 (number, required) - ID of the user

+ Response 200

    [User][]

### Update a User [PATCH]
To update a User send a JSON with updated value for one or more of the User resource attributes. It is possible to modify every field.

+ Request (application/json)

        {
            "name": "Sonia"
        }


+ Response 200

    [User][]

### Delete a User [DELETE]
Removal of the user with an Id

+ Response 204


## User Collection [/users{?filter}]

A resource representing all of my Users in the system. This is an array of users

+ Attributes(UsersStruct)

+ Model (application/json)

    JSON representation of user Collection Resource.

    + Headers

            Authentication: <user_token> - To have acces to this resource the user has to be identified 
    + Body

            [
              {
                "id": 1,
                "name": "Sonia",
                "first_surname": "Lolo",
                "second_surname": "Aria",
                "nickname": "Sonya",
                "email": "sonialolo@gmail.com:",
                "birthday": "1984-01-12",
                "studies": [
                  "journalism",
                  "psychology"
                ],
                "porfessions": [
                  "teacher",
                  "psychologist"
                ],
                "prev_volunteering": [
                  "AMI3"
                ],
                "published_at": "2016",
                "rol": "user"
              }
            ]

### List every Users [GET]
Return a list of the users

+ Parameters
  + filter: "%7B%22porfessions%22%3A+%22teacher%22%7D" (string, optional) - Different filters we are goinf to use. In this example we are using {"porfessions": "teacher"}

+ Response 200
  [User Collection][]

### Create a User [POST]
Creates a new User. You should fill in the every fields.

+ Request (application/json)

        {
          "name": "Sonia",
          "first_surname": "Lolo",
          "second_surname": "Aria",
          "nickname": "Sonya",
          "email": "sonialolo@gmail.com:",
          "birthday": "1984",
          "studies": [
            "journalism",
            "psychology"
          ],
          "porfessions": [
            "teacher",
            "psychologist"
          ],
          "prev_volunteering": [
            "AMI3"
          ],
          "published_at": "2016",
          "rol": "user"
        }

+ Response 200
  [User][]


# Group Visits 
Every resource related with the Visits

## Visit [/visits/{visit_id}]
The users do visits to the participants houses. The resource visit has the next fields:

name | example_value | kind_value | requiered | description
--:| ---- | --- | --- | --- 
id|1|number|required|Visit Id
sheet_id|1|number|true|Sheet Id
user_id|1|number|true|Id of user who is goint to do or update the sheet  
date|2018/04/04|string|true|Date when the visit is done
state|pendient|string|true|State of the visit(pendient, incomplete, done) --:| ---- | --- | --- | --- 




+ Parameters
  + visit_id: 1 (number,required) - ID of the visit

+ Attributes(VisitStructure)


+ Model (application/json)

    JSON representation of Visit Resource.

    + Headers

            Authentication: <user_token> - To have acces to this resource the user has to be identified 

    + Body

            {
              "id": 1,
              "sheet_id": 1,
              "user_id": 1,
              "date": "2018/04/04",
              "state": "pendient"
            }

### View Visit Details [GET]

Retrieve a user with the given id

+ Response 200
  [Visit][]


### Update a Visit [PATCH]
+ Request (application/json)

        {
            "date": "2018/04/04"
        }

+ Response 200

    [Visit][]

### Delete a Visit [DELETE]
Removal of a visit

+ Response 204

## Visit Collection [/visits{?filter}]

A resource representing all of my Visitis in the system.

+ Attributes(VisitsStructure)

+ Model (application/json)

    JSON representation of Visit Collection Resource.

    + Headers

            Authentication: <user_token> - To have acces to this resource the user has to be identified 
    + Body

            [
              {
                "id": 1,
                "sheet_id": 1,
                "user_id": 1,
                "date": "2018/04/04",
                "state": "pendient"
              }
            ]

### List every Visits [GET]
Return a list of your Visits

+ Parameters
  + filter: "%7B%E2%80%98zone%E2%80%99%3A%E2%80%98Chiclayo%E2%80%99%7D" (string, optional) - Different filters we are goinf to use. Originaly this filter is {'zone':'Chiclayo'}

+ Response 200
  [Visit Collection][]

### Create a Visit [POST]
Creates a new User.

+ Request (application/json)

        {
          "sheet_id": 1,
          "user_id": 1,
          "date": "2018/04/04",
          "state": "pendient"
        }

+ Response 200
  [Visit][]


# Group States

## State [/states/{state_id}]
The are in some fields of the sheets Those save historical fields. The resource State has the next fields:

name | example_value | kind_value | requiered | description
--:| ---- | --- | --- | --- 
id|4|number|true|Id of the current state
prev_state|3|number|true|Id of the previous value
id|4|number|true|Id of the current state
value|{"name":"Angel Mary"}|any|true|Any kind of variable
timestamp| Wed Feb 28 2018 17:02:43 GMT+0100|string|true|Date of record data
user_id| 3|number|true|Id of the user who modify the field

+ Parameters
  + state_id: 1 (number,required) - ID of the object

+ Attributes (StateStruct)


+ Model (application/json)

    JSON representation of Visit Resource.

    + Headers

            Authentication: <user_token> - To have acces to this resource the user has to be identified 

    + Body

            {
              "id": 4,
              "prev_state":2,
              "value":
              {
                "diagnsose": "Autism",
                "start_year": 1993
              },
              "timestamp": "2018/04/04",
              "user_id": 3, 
            }

### View State Details [GET]

Retrieve a state with the given id

+ Response 200
  [State][]


### Update a State [PATCH]
+ Request (application/json)

        {
            "value": 
              {
                "diagnsose": "Down's Syndrome",
                "start_year": 1993
              }
        }

+ Response 200

            {
              "id": 4,
              "prev_state": 3,
              "value": 
                {
                  "diagnsose": "Down's Syndrome",
                  "start_year": 1993
                },
              "timestamp": "2018/04/04",
              "user_id": 3, 
            }

### Delete a State [DELETE]
Removal of a state
+ Response 204 

## State Collection [/states{?filter}]

A resource representing all of my States in the system.

+ Attributes(StatesStruct)

+ Model (application/json)

    JSON representation of State Collection Resource.

    + Headers

            Authentication: <user_token> - To have acces to this resource the user has to be identified 
    + Body

            [
              {
                "id": 4,
                "prev_state": 3,
                "value":
                  {
                    "diagnsose": "Autism",
                    "start_year": 1993
                  },
                "timestamp": "2018/04/04",
                "user_id": 3, 
                "sheet_id": 2
              }
            ]

### List every States [GET]
Return a list of your states

+ Parameters
  + filter: "%7B%E2%80%98zone%E2%80%99%3A%E2%80%98Chiclayo%E2%80%99%7D" (string, optional) - Different filters we are goinf to use. Originaly this filter is {'sheet_id':1}

+ Response 200
  [State Collection][]

### Create a State [POST]
Creates a new State.

+ Request (application/json)

        {
          "id": 4,
          "prev_state": 3,
          "id": 4,
          "value":
            {
              "diagnsose": "Autism",
              "start_year": 1993
            },
          "timestamp": "2018/04/04",
          "user_id": 3, 
          "sheet_id": 2
        }
+ Response 200
  [State][]


# Group Sheets

## Sheet [/sheets/{sheet_id}]
The information of every participant will be store in sheets. The resource Sheet has the next fields:

name | example_value | kind_value | requiered | description
--:| ---- | --- | --- | --- 
id|1|number|required|Sheet ID
name|Carlos|string|required|Name of the participant
first_surname| Vilchez |string|required|Participant first surname
second_surname| Orlandini|string|false|Participant second surname
bthday| 1993/04/21|string|false|Participant birthday
dni| 702076478x |string|false| Participant DNI
zone|Chiclayo|string|required|Zona where the participant is living
address| Pueblo Joven 4 de Noviembre 23, |string|required| Participant address
family_fotos|url1,url2|array[State]|false| List of State Object pointing to the urls family photos
house_photos|url1,url2|array[State]|false| List of State Object pointing to the urls house photos
responsible|State|array[State]|false|List of State Object with the responsible information
family_information|State|array[State]|false| List of State Object with family information
center|State|array[State]|false|List of State Object with the center information
therapies|State|array[State]|false|List of State Object with therapy information
social_situation|State|array[State]|false| List of State Object with sovial situation information 
medical_info|State|array[State]|false|List of State Object with medical information
home_info|State|array[State]|false| List of State Object with house information
economic_info|State|array[State]|false|  List of State Object with economical information
general_information|State|array[State]|false | List of State Object with general information
manifested_information|State|array[State]|false| List of State Object with manifested informationf
detected_information|State|array[State]|false| List of State Object with detected information
warning_information|State|array[State]|false| List of State Object with warning information
complete|false|boolean|required|false if the sheet requires further attention to fill the information


+ Parameters
  + sheet_id: 1 (number,required) - ID of the sheet

+ Attributes(object)




+ Model (application/json)

    JSON representation of Sheet Resource.

    + Headers

            Authentication: <user_token> - To have acces to this resource the user has to be identified 
    + Body

            {  
              "id":1,
              "name":"Carlos",
              "first_surname":"Vilchez",
              "second_surname":"Orlandini",
              "bthday":"1993/04/21",
              "dni":"702076478x",
              "zone":"Chiclayo",
              "address":"Pueblo Joven 4 de Noviembre 23, Chiclayo",
              "family_fotos":[  
                {  
                  "prev_state":null,
                  "state_id":1,
                  "value":{  
                    "urls":[  
                      "<url1>",
                      "<url2>"
                    ],
                    "time":"2018/04/02"
                  },
                  "timestamp":"2018/04/04",
                  "user_id":3
                }
              ],
              "family_information":[  
                {  
                  "prev_state":null,
                  "state_id":2,
                  "value":[  
                    {  
                      "name":"Noelia",
                      "first_surname":"Perez",
                      "second_surname":"Vilchez",
                      "bthday":"1990/05/21",
                      "relation":"sister",
                      "coexistence":"yes",
                      "study_work":"study",
                      "observations":"She does not do anything at home"
                    }
                  ],
                  "timestamp":"2018/04/04",
                  "user_id":3
                }
              ],
              "center":[  
                {  
                  "prev_state":null,
                  "state_id":3,
                  "value":{  
                    "start_year":2015,
                    "name":"Angel Mary",
                    "observations":""
                  },
                  "timestamp":"2018/04/04",
                  "user_id":3
                },
                {  
                  "prev_state":3,
                  "state_id": 21,
                  "value":{  
                    "start_year":2017,
                    "name":"Katuwira",
                    "observations":""
                  },
                  "timestamp":"2018/10/04",
                  "user_id":3
                }
              ],
              "therapies":[  
                {  
                  "prev_state":null,
                  "state_id": 4,
                  "value":{  
                    "center":"AFAPED",
                    "start_year":2016,
                    "asistance":"Perfect",
                    "observations":""
                  },
                  "timestamp":"2018/04/04",
                  "user_id":3
                }
              ],
              "social_situation":[  
                {  
                  "prev_state":null,
                  "state_id":5,
                  "value":{  
                    "free_time":"Football",
                    "minders":"mother",
                    "close_support":"grandmother",
                    "enviornment_relationship":"good",
                    "observations":""
                  },
                  "timestamp":"2018/04/04",
                  "user_id":3
                }
              ],
              "medical_info":{  
                "diagnose":[  
                  {  
                    "prev_state":null,
                    "state_id":6,
                    "value":{  
                      "diagnsose":"Autism",
                      "start_year":1996
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "mobility":[  
                  {  
                    "prev_state":null,
                    "state_id":7,
                    "value":{  
                      "movements":"Little tasks",
                      "wheelchair":"no",
                      "observations":""
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "comunication":[  
                  {  
                    "prev_state":null,
                    "state_id":8,
                    "value":{  
                      "level":"A few words"
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "tests":[  
                  {  
                    "prev_state":null,
                    "state_id":9,
                    "value":{  
                      "name":"Tac",
                      "year":"2017",
                      "observations":""
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "treatment":[  
                  {  
                    "prev_state":null,
                    "state_id":10,
                    "value":{  
                      "name":"Vitamains",
                      "year":"2017",
                      "observations":""
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "relative_disease":[  
                  {  
                    "prev_state":null,
                    "state_id":11,
                    "value":{  
                      "name":"Altheimer",
                      "relation":"Father",
                      "observations":"He has to eat C Vitamins every day"
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ]
              },
              "home_info":[  
                {  
                  "prev_state":null,
                  "state_id":12,
                  "value":{  
                    "own_rent":"rent",
                    "material":"Adobe",
                    "facilities":[  
                      "tv",
                      "water",
                      "light"
                    ],
                    "num_rooms":2,
                    "num_beds":3,
                    "forniture":"They have everything",
                    "salubrity":"Perfect",
                    "observations":"They have a holl in one wall"
                  },
                  "timestamp":"2018/04/04",
                  "user_id":3
                }
              ],
              "helps":{  
                "familiar_income":[  
                  {  
                    "prev_state":null,
                    "state_id":13,
                    "value":{  
                      "amount":1000,
                      "observations":""
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "external_support":[  
                  {  
                    "prev_state":null,
                    "state_id":14,
                    "value":{  
                      "name":"Altheimer",
                      "relation":"Father",
                      "observations":""
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "feeding_center":[  
                  {  
                    "prev_state":null,
                    "state_id":15,
                    "value":{  
                      "name":"Nuestra guia",
                      "start_year":"2017",
                      "observations":""
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "others":[  
                  {  
                    "prev_state":null,
                    "state_id":16,
                    "value":{  
                      "observations":""
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ]
              },
              "general_information":[  
                {  
                  "prev_state":null,
                  "state_id":17,
                  "value":{  
                    "message":"Carlos is geting better and better"
                  },
                  "timestamp":"2018/04/04",
                  "user_id":3
                }
              ],
              "manifested_information":[  
                {  
                  "prev_state":null,
                  "state_id":18,
                  "value":{  
                    "message":"The mother needs a work "
                  },
                  "timestamp":"2018/04/04",
                  "user_id":3
                }
              ],
              "detected_information":[  
                {  
                  "prev_state":null,
                  "state_id":19,
                  "value":{  
                    "message":"Carlos need more language therapy"
                  },
                  "timestamp":"2018/04/04",
                  "user_id":3
                }
              ],
              "warning_information":[  
                {  
                  "prev_state":null,
                  "state_id":20,
                  "value":{  
                    "message":"Language therapy!"
                  },
                  "timestamp":"2018/04/04",
                  "user_id":3
                }
              ],
              "complete": false
            }

### View Sheet Details [GET]

Retrieve a sheet with the given id

+ Response 200
  [Sheet][]


### Update a Sheet [PATCH]
+ Request (application/json)

        {
          "name": "Carlos",
          "first_surname": "Vilchez",
        }

+ Response 200
  [Sheet][]

### Delete a Sheet [DELETE]
Removal of a Sheet
+ Response 204

## Sheet Collection [/sheets{?filter}]

A resource representing all of my Sheets in the system.

+ Attributes(array[Sheet])

+ Model (application/json)

    JSON representation of State Collection Resource.

    + Headers

            Authentication: <user_token> - To have acces to this resource the user has to be identified 
    + Body

            [

              {  
                "id":1,
                "name":"Carlos",
                "first_surname":"Vilchez",
                "second_surname":"Orlandini",
                "bthday":"1993/04/21",
                "dni":"702076478x",
                "zone":"Chiclayo",
                "address":"Pueblo Joven 4 de Noviembre 23, Chiclayo",
                "family_fotos":[  
                  {  
                    "prev_state":3,
                    "state_id":4,
                    "value":{  
                      "urls":[  
                        "<url1>",
                        "<url2>"
                      ],
                      "time":"2018/04/02"
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "family_information":[  
                  {  
                    "prev_state":3,
                    "state_id":4,
                    "value":[  
                      {  
                        "name":"Noelia",
                        "first_surname":"Perez",
                        "second_surname":"Vilchez",
                        "bthday":"1990/05/21",
                        "relation":"sister",
                        "coexistence":"yes",
                        "study_work":"study",
                        "observations":"She does not do anything at home"
                      }
                    ],
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "center":[  
                  {  
                    "prev_state":null,
                    "state_id":3,
                    "value":{  
                      "start_year":2015,
                      "name":"Angel Mary",
                      "observations":""
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  },
                  {  
                    "prev_state":3,
                    "state_id":4,
                    "value":{  
                      "start_year":2017,
                      "name":"Katuwira",
                      "observations":""
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "therapies":[  
                  {  
                    "prev_state":null,
                    "state_id":4,
                    "value":{  
                      "center":"AFAPED",
                      "start_year":2016,
                      "asistance":"Perfect",
                      "observations":""
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "social_situation":[  
                  {  
                    "prev_state":null,
                    "state_id":4,
                    "value":{  
                      "free_time":"Football",
                      "minders":"mother",
                      "close_support":"grandmother",
                      "enviornment_relationship":"good",
                      "observations":""
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "medical_info":{  
                  "diagnose":[  
                    {  
                      "prev_state":null,
                      "state_id":4,
                      "value":{  
                        "diagnsose":"Autism",
                        "start_year":1996
                      },
                      "timestamp":"2018/04/04",
                      "user_id":3
                    }
                  ],
                  "mobility":[  
                    {  
                      "prev_state":null,
                      "state_id":4,
                      "value":{  
                        "movements":"Little tasks",
                        "wheelchair":"no",
                        "observations":""
                      },
                      "timestamp":"2018/04/04",
                      "user_id":3
                    }
                  ],
                  "comunication":[  
                    {  
                      "prev_state":null,
                      "state_id":4,
                      "value":{  
                        "level":"A few words"
                      },
                      "timestamp":"2018/04/04",
                      "user_id":3
                    }
                  ],
                  "tests":[  
                    {  
                      "prev_state":null,
                      "state_id":4,
                      "value":{  
                        "name":"Tac",
                        "year":"2017",
                        "observations":""
                      },
                      "timestamp":"2018/04/04",
                      "user_id":3
                    }
                  ],
                  "treatment":[  
                    {  
                      "prev_state":null,
                      "state_id":4,
                      "value":{  
                        "name":"Vitamains",
                        "year":"2017",
                        "observations":""
                      },
                      "timestamp":"2018/04/04",
                      "user_id":3
                    }
                  ],
                  "relative_disease":[  
                    {  
                      "prev_state":null,
                      "state_id":4,
                      "value":{  
                        "name":"Altheimer",
                        "relation":"Father",
                        "observations":"He has to eat C Vitamins every day"
                      },
                      "timestamp":"2018/04/04",
                      "user_id":3
                    }
                  ]
                },
                "home_info":[  
                  {  
                    "prev_state":3,
                    "state_id":4,
                    "value":{  
                      "own_rent":"rent",
                      "material":"Adobe",
                      "facilities":[  
                        "tv",
                        "water",
                        "light"
                      ],
                      "num_rooms":2,
                      "num_beds":3,
                      "forniture":"They have everything",
                      "salubrity":"Perfect",
                      "observations":"They have a holl in one wall"
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "helps":{  
                  "familiar_income":[  
                    {  
                      "prev_state":null,
                      "state_id":4,
                      "value":{  
                        "amount":1000,
                        "observations":""
                      },
                      "timestamp":"2018/04/04",
                      "user_id":3
                    }
                  ],
                  "external_support":[  
                    {  
                      "prev_state":null,
                      "state_id":4,
                      "value":{  
                        "name":"Altheimer",
                        "relation":"Father",
                        "observations":""
                      },
                      "timestamp":"2018/04/04",
                      "user_id":3
                    }
                  ],
                  "feeding_center":[  
                    {  
                      "prev_state":null,
                      "state_id":4,
                      "value":{  
                        "name":"Nuestra guia",
                        "start_year":"2017",
                        "observations":""
                      },
                      "timestamp":"2018/04/04",
                      "user_id":3
                    }
                  ],
                  "others":[  
                    {  
                      "prev_state":null,
                      "state_id":4,
                      "value":{  
                        "observations":""
                      },
                      "timestamp":"2018/04/04",
                      "user_id":3
                    }
                  ]
                },
                "general_information":[  
                  {  
                    "prev_state":null,
                    "state_id":4,
                    "value":{  
                      "message":"Carlos is geting better and better"
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "manifested_information":[  
                  {  
                    "prev_state":3,
                    "state_id":4,
                    "value":{  
                      "message":"The mother needs a work "
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "detected_information":[  
                  {  
                    "prev_state":3,
                    "state_id":4,
                    "value":{  
                      "message":"Carlos need more language therapy"
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "warning_information":[  
                  {  
                    "prev_state":3,
                    "state_id":4,
                    "value":{  
                      "message":"Language therapy!"
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "pendig":"yes"
              }

            ]

### List every Sheet [GET]
Return a list of your sheet

+ Parameters
  + filter: "%7B%E2%80%98zone%E2%80%99%3A%E2%80%98Chiclayo%E2%80%99%7D" (string, optional) - Different filters we are going to use. Originaly this filter is {'zone':'Chiclayo'}

+ Response 200
  [Sheet Collection][]

### Create a Sheet [POST]
Creates a new Sheet.

+ Request (application/json)

            {  
              "name":"Carlos",
              "first_surname":"Vilchez",
              "second_surname":"Orlandini",
              "bthday":"1993/04/21",
              "dni":"702076478x",
              "zone":"Chiclayo",
              "address":"Pueblo Joven 4 de Noviembre 23, Chiclayo",
              "family_fotos":[  
                {  
                  "prev_state":3,
                  "state_id":4,
                  "value":{  
                    "urls":[  
                      "<url1>",
                      "<url2>"
                    ],
                    "time":"2018/04/02"
                  },
                  "timestamp":"2018/04/04",
                  "user_id":3
                }
              ],
              "family_information":[  
                {  
                  "prev_state":3,
                  "state_id":4,
                  "value":[  
                    {  
                      "name":"Noelia",
                      "first_surname":"Perez",
                      "second_surname":"Vilchez",
                      "bthday":"1990/05/21",
                      "relation":"sister",
                      "coexistence":"yes",
                      "study_work":"study",
                      "observations":"She does not do anything at home"
                    }
                  ],
                  "timestamp":"2018/04/04",
                  "user_id":3
                }
              ],
              "center":[  
                {  
                  "prev_state":null,
                  "state_id":3,
                  "value":{  
                    "start_year":2015,
                    "name":"Angel Mary",
                    "observations":""
                  },
                  "timestamp":"2018/04/04",
                  "user_id":3
                },
                {  
                  "prev_state":3,
                  "state_id":4,
                  "value":{  
                    "start_year":2017,
                    "name":"Katuwira",
                    "observations":""
                  },
                  "timestamp":"2018/04/04",
                  "user_id":3
                }
              ],
              "therapies":[  
                {  
                  "prev_state":null,
                  "state_id":4,
                  "value":{  
                    "center":"AFAPED",
                    "start_year":2016,
                    "asistance":"Perfect",
                    "observations":""
                  },
                  "timestamp":"2018/04/04",
                  "user_id":3
                }
              ],
              "social_situation":[  
                {  
                  "prev_state":null,
                  "state_id":4,
                  "value":{  
                    "free_time":"Football",
                    "minders":"mother",
                    "close_support":"grandmother",
                    "enviornment_relationship":"good",
                    "observations":""
                  },
                  "timestamp":"2018/04/04",
                  "user_id":3
                }
              ],
              "medical_info":{  
                "diagnose":[  
                  {  
                    "prev_state":null,
                    "state_id":4,
                    "value":{  
                      "diagnsose":"Autism",
                      "start_year":1996
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "mobility":[  
                  {  
                    "prev_state":null,
                    "state_id":4,
                    "value":{  
                      "movements":"Little tasks",
                      "wheelchair":"no",
                      "observations":""
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "comunication":[  
                  {  
                    "prev_state":null,
                    "state_id":4,
                    "value":{  
                      "level":"A few words"
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "tests":[  
                  {  
                    "prev_state":null,
                    "state_id":4,
                    "value":{  
                      "name":"Tac",
                      "year":"2017",
                      "observations":""
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "treatment":[  
                  {  
                    "prev_state":null,
                    "state_id":4,
                    "value":{  
                      "name":"Vitamains",
                      "year":"2017",
                      "observations":""
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "relative_disease":[  
                  {  
                    "prev_state":null,
                    "state_id":4,
                    "value":{  
                      "name":"Altheimer",
                      "relation":"Father",
                      "observations":"He has to eat C Vitamins every day"
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ]
              },
              "home_info":[  
                {  
                  "prev_state":3,
                  "state_id":4,
                  "value":{  
                    "own_rent":"rent",
                    "material":"Adobe",
                    "facilities":[  
                      "tv",
                      "water",
                      "light"
                    ],
                    "num_rooms":2,
                    "num_beds":3,
                    "forniture":"They have everything",
                    "salubrity":"Perfect",
                    "observations":"They have a holl in one wall"
                  },
                  "timestamp":"2018/04/04",
                  "user_id":3
                }
              ],
              "helps":{  
                "familiar_income":[  
                  {  
                    "prev_state":null,
                    "state_id":4,
                    "value":{  
                      "amount":1000,
                      "observations":""
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "external_support":[  
                  {  
                    "prev_state":null,
                    "state_id":4,
                    "value":{  
                      "name":"Altheimer",
                      "relation":"Father",
                      "observations":""
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "feeding_center":[  
                  {  
                    "prev_state":null,
                    "state_id":4,
                    "value":{  
                      "name":"Nuestra guia",
                      "start_year":"2017",
                      "observations":""
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ],
                "others":[  
                  {  
                    "prev_state":null,
                    "state_id":4,
                    "value":{  
                      "observations":""
                    },
                    "timestamp":"2018/04/04",
                    "user_id":3
                  }
                ]
              },
              "general_information":[  
                {  
                  "prev_state":null,
                  "state_id":4,
                  "value":{  
                    "message":"Carlos is geting better and better"
                  },
                  "timestamp":"2018/04/04",
                  "user_id":3
                }
              ],
              "manifested_information":[  
                {  
                  "prev_state":3,
                  "state_id":4,
                  "value":{  
                    "message":"The mother needs a work "
                  },
                  "timestamp":"2018/04/04",
                  "user_id":3
                }
              ],
              "detected_information":[  
                {  
                  "prev_state":3,
                  "state_id":4,
                  "value":{  
                    "message":"Carlos need more language therapy"
                  },
                  "timestamp":"2018/04/04",
                  "user_id":3
                }
              ],
              "warning_information":[  
                {  
                  "prev_state":3,
                  "state_id":4,
                  "value":{  
                    "message":"Language therapy!"
                  },
                  "timestamp":"2018/04/04",
                  "user_id":3
                }
              ],
              "pendig":"yes"
            }

+ Response 200
  [Sheet][]

