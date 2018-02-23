FORMAT: 1A

# KoriNGO

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
  + studies: ["journalism","psychology"] (array[string]) - Collection of the studies 
  + porfessions: ["teacher","psychologist"] (array[string]) - Collection of different professions
  + previous_volunteering: ["AMI3"] (array[string]) - Collection of different volunteering
  + published_at: 2016-03-05 (string, required) - An ISO8601 date when the user is created
  + rol: user (string,required) - Admin or user(normal user)

### View Users Detail [GET]
Retrieve a user with the given id

+ Response 200 (application/json)
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

+ Response 200 (application/json)
  + Attributes(array[Users])

### Create a User [POST]
Creates a new User.


+ Attributes (object)
  + id_user: 1 (number, requiered)
  + name: Sonia (string,required)
  + first_surname: Lolo (string,required)
  + second_surname: Aria (string,required)
  + nickname: Sonya (string,required)
  + password: katuwira (password,required)
  + email: sonialolo@gmail.com: (email,required)
  + birthday: 1984-01-12 (date,required)
  + studies: journalism,psychology (array[string]) - Collection of the studies 
  + porfessions: teacher,psychologist (array[string]) - Collection of different professions
  + previous_volunteering: AMI3 (array[string]) - Collection of different volunteering
  + rol: user (string,required) - Admin or user(normal user)

+ Request (application/json)
  + Headers
    + Authentication: <user_token>
+ Response 200 (application/json)
  + Attributes (User)


### Update a user [PUT]
Update infromation of some user
+ Request (application/json)
  + Attributes (User)
+ Response 200 (application/json)
  + Attributes (User)


### Delete a user [POST]
//Borra todo el recursoo????
### Login user [POST]
//hay que hacerlo??

# Group Sheets 
Here is every resource related with the sheets

## State [/states/{state_id}]
  + Parameters
  + state_id: 1 (required, number) - ID of the state

// Hay que poner required en los campos idUser y date?? campos? No se rellenan cuando se crea la ficha
+ Attributes(object)
  + prev_value(string) - Value of previus value
  + current_value(string) -Value of the current value

## Sheet [/Sheets/{sheet_id}]
+ Parameters
  + question_id: 1 (required, number) - ID of the thecnical sheet



//podemos dejar vacio el campo prev_value??
// Donde ponemos las opciones del checkBox o el los select??
// Pensar forniture y salubrity



+ Attributes(object)
  + id_sheet: 1 (number, requiered)
  + name: Carlos (string,required)
  + first_surname: Vilchez (string,required)
  + second_surname: Orlandini (string,required)
  + bthday: 1993/04/21
  + dni: 702076478x (string,required)
  + zone: Chiclayo (string,required)
  + address: Pueblo Joven 4 de Noviembre 23, Chiclayo: (email,required)
  + family_photos(array[State]) - Array of State Object
    + prev_value (array[string]) - <url1>,<url2> (array[string]) - Array of previous family url photos 
    + current_value (array[string]) - <url1>,<url2> (array[string]) - Array of  current family url photos 
  + house_photos:  (array[State]) - Array of State Object
    + prev_value: (array[string]) - <url1>,<url2> (array[string]) - Array of previous houses url photos 
    + current_value: (array[string]) - <url1>,<url2> (array[string]) - Array of  current houses url photos

  + responsible (array[State]) - Array of State object
    + prev_value (object) - Previous responsible object
    + current_value (object) - Current responsible object
      + name: Rita (string, requiered) - Responsible name
      + first_surname: Vilchez (string, requiered) - Responsible first surname
      + second_surname: Orlandini (string, requiered) - Responsible second surname
      + relation: mother (string, requiered) - Relation with the participant
      + coexistence: yes (string, requiered) - Coexistence with the participant
      + suty_work: home (string, requiered) - Name of the studies or work
      + DNI: 30020330C (string, requiered) - Responsible DNI
      + tel:733829289 (string, requiered) - Resoinsible telephone

  + family_information(array[Sate]) - Array of State object  
    + prev_value (array[object]) - Previous field
    + current_value (array[object]) - Current field
      + family_info (object)
        + name: Noelia (string, requiered) - Relative name
        + first_surname: Perez (string, requiered) - Relative first surname
        + second_surname: Orlandini (string, requiered) - Relative second surname
        + relation: sister (string, requiered) - Relation with the participant
        + coexistence: yes (string, requiered) - Coexistence with the participant (yes, no, sometimes)
        + suty_work: home (string, requiered) - Name of the studies or work
        + observations: She does not do anything when she is at home (string, required)  - Relative observation
        + observations (string, required) - General observations

  + center: (array[State]) - Array of Status Object. School
    + prev_value (object) - Previous field
      + name: Angel Mary (string, required) - Name of the school
      + start_year : 2015 (number,required) - Year of entry
    + current_value: (object) - Current field
      + name: Katuwira (string, required) - Name of the school
      + start_year : 2015 (number,required) - Year of entry

  + therapies(array[State]) - Array of State object  
    + prev_value (object) - Previous field
    + current_value (object) - Current field
      + therapy: language therapy(string, required) - Kind of therapy
      + center: AFAPED(string, required) - Center of therapy
      + start_year:2015 (number, required) - Start year
      + asistence: perfect (string, required) - Asistence to the center of therapy (nothing, a litle, normal, good, perfect)
      + observations: Every year Carlos learn new words (string, required) - General observations
      
  + social_situation: array(State)
    + prev_value (array[object]) - Previous field
    + current_value (object) - Current field
      + free_time: pelota,tv (array[string], required) - Free time activities
      + minders: mother (array[string], required) - Participants minder
      + close_support:grandmother (array[string], required) - Close supports
      + enviornment_relationship: good (string, required) - Realationship with the enviornment (nothing, a litle, normal, good, perfect)
      + observations: Carlos spend most of the time at home (string, required) - General observations

  + medical_info (array[State])
    + prev_value (array[object]) - Previous field
    + current_value (object) - Current field
      + diagnose (object) - Diagnose
       + name 
       + year: 2010 (number,optional) - Year of the diagnose
    + Movility: little tasks (string, required) - Checkbox with different options
    + wheelchair: no (string, required) - use of wheelchair
    + comunication (object) 
        +level: a few words (string, required) - Checkbox with different options
    + tests (array[object])
      + name: tac (string,requiered) - Name of the test
      + year: 2012 (number) - Year of the test 
      + observations: He did this thest when he was 19 (string, required) - General observationsƒ

    + treatment (array[object])
      + name: vitmains (string,requiered) - Name of the test
      + year: 2013 (number) - Year of the test 
      + observations: He has to eat C vitmains every day (string, required) - General observations

    + relative_disease (array[object]) - Relatives diseases  
        + name: alzheimer (string) - Disease name
        + relation: father (string) - Relation with the participant
        + observations: He has to eat C vitmains every day (string, required) - General observations

  + home_info (array[State])
    + prev_value (array[object]) - Previous field
    + current_value (object) - Current field
      + own_rent: rent (string,required) - Ownership or rental house
      + material: adobe (string,required) - Mateial of construction (bricks, adobe, others)
      + facilities: tv,water,Light (array[string],required) - Facilities of the house (water, gas, light, bathroom, tv, dvd, speakers)
      + num_rooms: 3 (number,required) - Room number of the house
      + num_beds: 4 (number,required) - Number of beds of the house
      + forniture: 
      + salubrity:  
      + observations: They have a holl in one wall (string, required) - General observations

  + economic_info (array[State])
    + prev_value (array[object]) - Previous field
    + current_value (object) - Current field
      + familar_income (array[object])
        + amount: 1000 (number, required) - income  family per month 
        + obserbations: The father is the only one working(string, required) - Familiar income observations
      + external_support: (array[object])
        + sponsorship:(array[object]) - List of sponsor
          + name: Afaped (string,required) - Name of the entity
          + start_year: 2015 (number,required) - Start year of sponsorship
          + amount: 50 (number) - Money amount every month 
        + feeding_center(array[object]) - List of feeding rooms  
          + name: Angel Mary (string,required) - Name of the feeding center
          + start_year: 2017 (string, required) - start year in the feeding room 
        + others: entry to the sport center (array[string]) - List of another supports
  
  + general_information (array[State])
    + prev_value (array[object]) - Previous field
    + current_value (object) - Current field
      + message: Carlos is geting better and better (string,required) - Message with the general information 

  + manifested_information (array[State])
    + prev_value (array[object]) - Previous field
    + current_value (object) - Current field
      + message: The mother needs a work (string,required) - Message with the manifested information 

  + detected_information (array[State])
    + prev_value (array[object]) - Previous field
    + current_value (object) - Current field
      + message: Carlos need more language therapy (string,required) - Message with the detected information 

  + warning_information (array[State])
    + prev_value (array[object]) - Previous field
    + current_value (object) - Current field
      + message: Language therapy!(string,required) - Message with the most important info. Short sentence. 

  + pendig: yes (string, required) - yes if we have to fill in more info afterwards



## Sheet [/visits/{visit_id}]

+ Parameters
  + visit_id: 1 (required, number) - ID of the visit


// Hay que poner required en los campos idUser y date?? campos? No se rellenan cuando se crea la ficha
+ Attributes(object)
  + id_visit: 1(number,required) - Visit Id
  + id_Sheet: 1(number,required) - Sheet Id
  + id_user: 1(number,required) - Id of user who is goint to do or update the sheet  
  + date: 2018/04/04 (string, required) - Date when the visit is done
  + state: pendient(string,requiered) - State of the visit(pendient, incomplete, done) 






