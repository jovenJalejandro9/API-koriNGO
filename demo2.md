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
  + published_at: 2016-03-05 (string, required) - An ISO8601 date when the user is created
  + rol: user (string,required) - Admin or user(normal user)


+ Model (application/hal+json)

    HAL+JSON representation of User Resource.

    + Headers

            Authentication: <user_token>

    + Body

            {
              "id_user": 1,
              "name": "Sonia",
              "first_surname": "Lolo",
              "second_surname": "Aria",
              "nickname": "Sonya",
              "password": "katuwira",
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
              "previous_volunteering": [
                "AMI3"
              ],
              "published_at": "2016",
              "rol": "user"
            }

### View Users Details [GET]

Retrieve a user with the given id
+ Response 200

    [User][]

### Update a User [PATCH]
To update a User send a JSON with updated value for one or more of the User resource attributes.

+ Request (application/json)

        {
            "name": "Sonia"
        }

+ Response 200

    [User][]

## User Collection [/users{?filter}]

A resource representing all of my Users in the system.

+ Attributes(array[User])

+ Model (application/hal+json)

    HAL+JSON representation of user Collection Resource.

    + Headers

            Authentication: <user_token>
    + Body

            [
              {
                "id_user": 1,
                "name": "Sonia",
                "first_surname": "Lolo",
                "second_surname": "Aria",
                "nickname": "Sonya",
                "password": "katuwira",
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
                "previous_volunteering": [
                  "AMI3"
                ],
                "published_at": "2016",
                "rol": "user"
              }
            ]

### List every Users [GET]
Return a list of your users

+ Parameters
  + filter: "%7B%22zone%22%3A%22Chiclayo%22%7D" (string, optional) - Different filters we are goinf to use. Originaly this filter is {'zone':'Chiclayo'}

+ Response 200
  [User Collection][]

### Create a User [POST]
Creates a new User.

+ Request (application/json)


        {
          "id_user": 1,
          "name": "Sonia",
          "first_surname": "Lolo",
          "second_surname": "Aria",
          "nickname": "Sonya",
          "password": "katuwira",
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
          "previous_volunteering": [
            "AMI3"
          ],
          "published_at": "2016",
          "rol": "user"
        }

+ Response 200
  [User][]

### Delete a User [DELETE]
+ Response 204

# Group Visits 
Every resource related with the Visits

## Visit [/visits/{visit_id}]

+ Parameters
  + visit_id: 1 (number,required) - ID of the visit

+ Attributes(object)
  + id_visit: 1(number,required) - Visit Id
  + id_Sheet: 1(number,required) - Sheet Id
  + id_user: 1(number,required) - Id of user who is goint to do or update the sheet  
  + date: 2018/04/04 (string, required) - Date when the visit is done
  + state: pendient(string,required) - State of the visit(pendient, incomplete, done) 

+ Model (application/hal+json)

    HAL+JSON representation of Visit Resource.

    + Headers

            Authentication: <user_token>

    + Body

            {
              "id_visit": 1,
              "id_Sheet": 1,
              "id_user": 1,
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

## Visit Collection [/visits{?filter}]

A resource representing all of my Visitis in the system.

+ Attributes(array[Visit])

+ Model (application/hal+json)

    HAL+JSON representation of Visit Collection Resource.

    + Headers

            Authentication: <user_token>
    + Body

            [
              {
                "id_visit": 1,
                "id_Sheet": 1,
                "id_user": 1,
                "date": "2018/04/04",
                "state": "pendient"
              }
            ]

### List every Visits [GET]
Return a list of your Visits

+ Parameters
  + filter: "%7B%22zone%22%3A%22Chiclayo%22%7D" (string, optional) - Different filters we are goinf to use. Originaly this filter is {'zone':'Chiclayo'}

+ Response 200
  [Visit Collection][]

### Create a Visit [POST]
Creates a new User.

+ Request (application/json)

        {
          "id_visit": 1,
          "id_Sheet": 1,
          "id_user": 1,
          "date": "2018/04/04",
          "state": "pendient"
        }

+ Response 200
  [Visit][]

### Delete a User [DELETE]
+ Response 204




## State [/states/{state_id}]

+ Parameters
  + state_id: 1 (number,required) - ID of the object

+ Attributes (object)
  + prev_state: 3(number, required) - Id of the previous value
  + id_state: 4(number,required) - Id of the current state
  + current_value (object,required) - Object with the current info
    + diagnsose: Autism(string,required) - Disagnose
    + start_year: 1993(number,required) - Diagnoise year 
  + timestamp: 2018/04/04 (string,required) - Date of record data
  + id_user: 3(number, required) - Id of the user who modify the field

+ Model (application/hal+json)

    HAL+JSON representation of Visit Resource.

    + Headers

            Authentication: <user_token>

    + Body

            {
              "prev_state":2,
              "id_state": 4,
              "current_value":
                [
                  {
                    "diagnsose": "Autism",
                    "start_year": 1993
                  }
                ],
              "timestamp": "2018/04/04",
              "id_user": 3, 
            }

### View State Details [GET]

Retrieve a state with the given id

+ Response 200
  [State][]


### Update a State [PATCH]
+ Request (application/json)

        {
            "current_value": 
              {
                "diagnsose": "Down's Syndrome",
                "start_year": 1993
              }
        }

+ Response 200

            {
              "prev_state": 3,
              "id_state": 4,
              "current_value": 
                {
                  "diagnsose": "Down's Syndrome",
                  "start_year": 1993
                },
              "timestamp": "2018/04/04",
              "id_user": 3, 
            }

## State Collection [/states{?filter}]

A resource representing all of my States in the system.

+ Attributes(array[State])

+ Model (application/hal+json)

    HAL+JSON representation of State Collection Resource.

    + Headers

            Authentication: <user_token>
    + Body

            [
              {
                "prev_state": 3,
                "id_state": 4,
                "current_value":
                  {
                    "diagnsose": "Autism",
                    "start_year": 1993
                  },
                "timestamp": "2018/04/04",
                "id_user": 3, 
                "id_sheet": 2
              }
            ]

### List every States [GET]
Return a list of your states

+ Parameters
  + filter: "%7B%22zone%22%3A%22Chiclayo%22%7D" (string, optional) - Different filters we are goinf to use. Originaly this filter is {'id_sheet':1}

+ Response 200
  [State Collection][]

### Create a State [POST]
Creates a new State.

+ Request (application/json)

        {
          "prev_state": 3,
          "id_state": 4,
          "current_value":
            {
              "diagnsose": "Autism",
              "start_year": 1993
            },
          "timestamp": "2018/04/04",
          "id_user": 3, 
          "id_sheet": 2
        }


+ Response 200
  [State][]

### Delete a State [DELETE]
+ Response 204


## Sheet [/sheets/{sheet_id}]

+ Parameters
  + sheet_id: 1 (number,required) - ID of the sheet

+ Attributes(object)
  + id_sheet: 1 (number, required)
  + name: Carlos (string,required)
  + first_surname: Vilchez (string,required)
  + second_surname: Orlandini (string,required)
  + bthday: 1993/04/21 (string,required)
  + dni: 702076478x (string,required)
  + zone: Chiclayo (string,required)
  + address: Pueblo Joven 4 de Noviembre 23, Chiclayo (string,required) - Participant address

  + family_fotos (array[State]) - List of State Object
  + house_photos  (array[State]) - Array of State Object
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

  + pendig: yes (string, required) - yes if we have to fill in more info afterwards




+ Model (application/hal+json)

    HAL+JSON representation of Sheet Resource.

    + Headers

            Authentication: <user_token>

    + Body

            {
               "id_sheet":1,
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
                     "id_state":4,
                     "current_value":{
                        "urls":[
                           "<url1>",
                           "<url2>"
                        ],
                        "time":"2018/04/02"
                     },
                     "timestamp":"2018/04/04",
                     "id_user":3
                  }
               ],
               "family_information":[
                  {
                     "prev_state":3,
                     "id_state":4,
                     "current_value":[
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
                     "id_user":3
                  }
               ],
               "center":[
                  {
                     "prev_state":null,
                     "id_state":3,
                     "current_value":{
                        "start_year":2015,
                        "name":"Angel Mary",
                        "observations":""
                     },
                     "timestamp":"2018/04/04",
                     "id_user":3
                  },
                  {
                     "prev_state":3,
                     "id_state":4,
                     "current_value":{
                        "start_year":2017,
                        "name":"Katuwira",
                        "observations":""
                     },
                     "timestamp":"2018/04/04",
                     "id_user":3
                  }
               ],
               "therapies":[
                  {
                     "prev_state":null,
                     "id_state":4,
                     "current_value":{
                        "center":"AFAPED",
                        "start_year":2016,
                        "asistance":"Perfect",
                        "observations":""
                     },
                     "timestamp":"2018/04/04",
                     "id_user":3
                  }
               ],
               "social_situation":[
                  {
                     "prev_state":null,
                     "id_state":4,
                     "current_value":{
                        "free_time":"Football",
                        "minders":"mother",
                        "close_support":"grandmother",
                        "enviornment_relationship":"good",
                        "observations":""
                     },
                     "timestamp":"2018/04/04",
                     "id_user":3
                  }
               ],
               "medical_info":{

                  
                  "mobility":[
                     {
                        "prev_state":null,
                        "id_state":4,
                        "current_value":{
                           "movements":"Little tasks",
                           "wheelchair":"no",
                           "observations":""
                        },
                        "timestamp":"2018/04/04",
                        "id_user":3
                     }
                  ]
               }
            }

### View Sheet Details [GET]

Retrieve a sheet with the given id

+ Response 200
  [Sheet][]


### Update a Sheet [PATCH]
+ Request (application/json)

        {
            
          "name": "Victor",
          "first_surname": "Perez",
            
        }

+ Response 200



## Sheet Collection [/sheets{?filter}]

A resource representing all of my Sheets in the system.

+ Attributes(array[Sheet])

+ Model (application/hal+json)

    HAL+JSON representation of State Collection Resource.

    + Headers

            Authentication: <user_token>
    + Body

            [
              {
                "id_sheet": 1,
                "name": "Carlos",
                "first_surname": "Vilchez",
                "second_surname": "Orlandini",
                "bthday": "1993/04/21",
                "dni": "702076478x",
                "zone": "Chiclayo",
                "address": "Pueblo Joven 4 de Noviembre 23, Chiclayo",
                "family_fotos": [
                  {
                    "prev_state": 3,
                    "id_state": 4,
                    "current_value": {
                      "urls": [<url1>,<url2>],
                      "time": "2018/04/02"
                    },
                    "timestamp": "2018/04/04",
                    "id_user": 3
                  }
                ],
                "house_photos": [
                  {
                    "prev_state": 3,
                    "id_state": 4,
                    "current_value": {
                      "urls": [<url1>,<url2>],
                      "time": "2018/04/02"
                    },
                    "timestamp": "2018/04/04",
                    "id_user": 3
                  }
                ],
                "responsible": [
                  {
                    "prev_state": 3,
                    "id_state": 4,
                    "current_value": {
                      "name": "Rita",
                      "first_surname": "Vilchez",
                      "second_surname": "Orlandini",
                      "bthday": "1980/03/21",
                      "relation": "mother",
                      "coexistence": "yes",
                      "study_work": "home",
                      "tel": "299303043",
                    },
                    "timestamp": "2018/04/04",
                    "id_user": 3
                  }
                ],

                "family_information": [
                  {
                    "prev_state": 3,
                    "id_state": 4,
                  "current_value": [
                    {
                      "name": "Noelia",
                      "first_surname": "Perez",
                      "second_surname": "Vilchez",
                      "bthday": "1990/05/21",                    
                      "relation": "sister",
                      "coexistence": "yes",
                      "study_work": "study",
                      "observations": "She does not do anything at home"
                    }
                  ],
                    "timestamp": "2018/04/04",
                    "id_user": 3
                  }
                ],

                "center": [
                  {
                    "prev_state": null,
                    "id_state": 3,
                    "current_value": {
                      "start_year": 2015,
                      "name": "Angel Mary",
                      "observations": ""
                    },
                    "timestamp": "2018/04/04",
                    "id_user": 3
                  },
                  {
                    "prev_state": 3,
                    "id_state": 4,
                    "current_value": {
                      "start_year": 2017,
                      "name": "Katuwira",
                      "observations": ""
                    },
                    "timestamp": "2018/04/04",
                    "id_user": 3
                  }
                ],
                "therapies": [
                  {
                    "prev_state": null,
                    "id_state": 4,
                    "current_value": {
                      "center": "AFAPED",
                      "start_year":2016,
                      "asistance": "Perfect",
                      "observations": ""
                    },
                    "timestamp": "2018/04/04",
                    "id_user": 3
                  }
                ],

                "social_situation": [
                  {
                    "prev_state": null,
                    "id_state": 4,
                    "current_value": {
                      "free_time": "Football",
                      "minders":"mother",
                      "close_support": "grandmother",
                      "enviornment_relationship": "good",
                      "observations": ""                  
                    },
                    "timestamp": "2018/04/04",
                    "id_user": 3
                  }
                ],

                "medical_info": {


                  diagnose:[
                    {
                      "prev_state": null,
                      "id_state": 4,
                      "current_value": {
                        "diagnsose": "Autism",
                        "start_year": 1996
                      },
                      "timestamp": "2018/04/04",
                      "id_user": 3
                    }
                  ],
                  Movility:[
                    {
                      "prev_state": null,
                      "id_state": 4,
                      "current_value": {
                        "movements": "Little tasks",
                        "wheelchair":"no",
                        "observations": ""  
                      },
                      "timestamp": "2018/04/04",
                      "id_user": 3
                    }
                  ],
                  comunication:[
                    {
                      "prev_state": null,
                      "id_state": 4,
                      "current_value": {
                        "level": "A few words"
                      },
                      "timestamp": "2018/04/04",
                      "id_user": 3
                    }
                  ],
                  tests:[
                    {
                      "prev_state": null,
                      "id_state": 4,
                      "current_value": {
                        "name": "Tac",
                        "year":"2017",
                        "observations": ""  
                      },
                      "timestamp": "2018/04/04",
                      "id_user": 3
                    }
                  ],
                  treatment:[
                    {
                      "prev_state": null,
                      "id_state": 4,
                      "current_value": {
                        "name": "Vitamains",
                        "year":"2017",
                        "observations": ""  
                      },
                      "timestamp": "2018/04/04",
                      "id_user": 3
                    }
                  ],
                  relative_disease:[
                    {
                      "prev_state": null,
                      "id_state": 4,
                      "current_value": {
                        "name": "Altheimer",
                        "relation":"Father",
                        "observations": "He has to eat C Vitamins every day"  
                      },
                      "timestamp": "2018/04/04",
                      "id_user": 3
                    }
                  ]
                },
                  
                

                  "home_info": [
                    {
                      "prev_state": 3,
                      "id_state": 4,
                      "current_value": {
                        "own_rent": "rent",
                        "material":"Adobe",
                        "facilities": ["tv","water","light"]
                        "num_rooms":"2",
                        "num_beds":"3",
                        "material":"Adobe",
                        "forniture":"They have everything",
                        "salubrity":"Perfect",
                        "observations": "They have a holl in one wall"    
                      },
                      "timestamp": "2018/04/04",
                      "id_user": 3
                    }
                  ],
                  "helps": {
                    familiar_income:[
                      {
                        "prev_state": null,
                        "id_state": 4,
                        "current_value": {
                          "amount": 1000,
                          "observations:""
                        },
                        "timestamp": "2018/04/04",
                        "id_user": 3
                      }
                    ],
                    external_support:[
                      {
                        "prev_state": null,
                        "id_state": 4,
                        "current_value": {
                          "name": "Altheimer",
                          "relation":"Father",
                          "observations": ""  
                        },
                        "timestamp": "2018/04/04",
                        "id_user": 3
                      }
                    ],
                    feeding_center:[
                      {
                        "prev_state": null,
                        "id_state": 4,
                        "current_value": {
                          "name": "Nuestra guia",
                          "start_year":"2017",
                          "observations": ""  
                        },
                        "timestamp": "2018/04/04",
                        "id_user": 3
                      }
                    ],
                    others:[
                      {
                        "prev_state": null,
                        "id_state": 4,
                        "current_value": {
                          "observations": ""  
                        },
                        "timestamp": "2018/04/04",
                        "id_user": 3
                      }
                    ]
                  }
                  "general_information": [
                    {
                      "prev_state": 3,
                      "id_state": 4,
                      "current_value": {
                        "message": "Carlos is geting better and better"
                      },
                      "timestamp": "2018/04/04",
                      "id_user": 3
                    }
                  ],
                  "manifested_information": [
                    {
                      "prev_state": 3,
                      "id_state": 4,
                      "current_value": {
                        "message": "The mother needs a work "
                      },
                      "timestamp": "2018/04/04",
                      "id_user": 3
                    }
                  ],
                  "detected_information": [
                    {
                      "prev_state": 3,
                      "id_state": 4,
                      "current_value": {
                        "message": "Carlos need more language therapy"
                      },
                      "timestamp": "2018/04/04",
                      "id_user": 3
                    }
                  ],
                  "warning_information": [
                    {
                      "prev_state": 3,
                      "id_state": 4,
                      "current_value": {
                        "message": "Language therapy!"
                      },
                      "timestamp": "2018/04/04",
                      "id_user": 3
                    }
                  ],
                  "pendig": "yes"
                }
              ]



### List every Sheet [GET]
Return a list of your sheet

+ Parameters
  + filter: "%7B%22zone%22%3A%22Chiclayo%22%7D" (string, optional) - Different filters we are goinf to use. Originaly this filter is {'zone':'Chiclayo'}

+ Response 200
  [Sheet Collection][]

### Create a Sheet [POST]
Creates a new Sheet.

+ Request (application/json)

  [Sheet][]


+ Response 200
  [Sheet][]

### Delete a State [DELETE]
+ Response 204