# MongoDB Practice
- Connect to a running mongo instance, use a database named mongo_practice.
- ![copyImage](https://github.com/user-attachments/assets/870974b8-94b1-4d7d-9f3e-43834a0e31db)
## Insert Documents
-Insert the following documents into a movies collection.

title : Fight Club
writer : Chuck Palahniuk
year : 1999
actors : [
  Brad Pitt
  Edward Norton
db.movies.insert({title:"Fight Club", writer: "Chuck Palahniuk", year: "1999", actors:["Brad Pitt", "Edward Norton"]})
![copyImage](https://github.com/user-attachments/assets/be543eda-dea9-4502-92f3-4254cd9afd90)

title : Pulp Fiction
writer : Quentin Tarantino
year : 1994
actors : [
  John Travolta
  Uma Thurman
]
 db.movies.insert({title:"Pulp Fiction", writer:"Quentin Tarantino", year:"2009", actors:["John Travolta", "Uma Thurman"]})
![copyImage](https://github.com/user-attachments/assets/64813c1a-e8dd-4b30-a83d-04904b40c643)

title : Inglorious Basterds
writer : Quentin Tarantino
year : 2009
actors : [
  Brad Pitt
  Diane Kruger
  Eli Roth
]
db.movies.insert({title:"Inglorious Basterds", writer:"Quentin Tarantino", year:"2009", actors:["Brad Pitt", "Diane Kruger", "Eli Roth"]})
![copyImage](https://github.com/user-attachments/assets/48db6152-4f82-4f1c-9393-455e10fb782c)

title : The Hobbit: An Unexpected Journey
writer : J.R.R. Tolkein
year : 2012
franchise : The Hobbit
db.movies.insert({title:"The Hobbit: An unexpected Journey", writer:"J.R.R. Tolkein", year:"2012",franchise:"The Hobbit"})
![copyImage](https://github.com/user-attachments/assets/8f80437e-7e91-41c6-87c6-1ac5d1bd5ae1)
title : The Hobbit: The Desolation of Smaug
writer : J.R.R. Tolkein
year : 2013
franchise : The Hobbit
db.movies.insert({title:"The Hobbit: The Desolation of Smaug", writer:"J.R.R Tolkien", year:"2013", franchise:"The Hobbit"})
![copyImage](https://github.com/user-attachments/assets/36e34c3c-e6f1-440c-ab52-83b98a06d6be)

title : The Hobbit: The Battle of the Five Armies
writer : J.R.R. Tolkein
year : 2012
franchise : The Hobbit
synopsis : Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness.
db.movies.insert({title:"The Hobbit: The Battle of the Five Armies", writer:"J.R.R Tolkien", year:"2002", franchise:"The Hobbit", synopsis:"Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness."})
![copyImage](https://github.com/user-attachments/assets/f686ab16-2e96-4a68-ae25-c68e3a5e55ad)

title : Pee Wee Herman's Big Adventure
db.movies.insert({title:"Pee Wee Herman's Big Adventures"})

![copyImage](https://github.com/user-attachments/assets/71fb2d83-3a91-43d9-b3ee-c872f5cfd438)

title : Avatar
 db.movies.insert({title:"Avatar"})
![copyImage](https://github.com/user-attachments/assets/1ccce125-6923-4a84-aeb3-55708caf6078)
## Query / Find Documents
get all documents
db.movies.find()
![copyImage](https://github.com/user-attachments/assets/ea06de7d-b625-41bf-8401-d3880e6c65de)
2. get all documents with `writer` set to "Quentin Tarantino"
db.movies.find({writer:"Quentin Tarantino"})
![copyImage](https://github.com/user-attachments/assets/8d788069-2c1b-429a-b99c-eaa7277688cd)

get all documents where actors include "Brad Pitt"
db.movies.find({actors:"Brad Pitt"})
![copyImage](https://github.com/user-attachments/assets/32251d67-c562-4b8a-bc98-3ca08ade67ff)

get all documents with franchise set to "The Hobbit"
db.movies.find({franchise:"The Hobbit"})
![copyImage](https://github.com/user-attachments/assets/75f8df3c-126d-463d-ac31-0c9d511958ec)

get all movies released in the 90s
db.movies.find({year:{$gt:"1990", $lt:"2000"}})
![copyImage](https://github.com/user-attachments/assets/53dd2a22-ce39-4ea9-ac72-932e6112fe5e)

get all movies released before the year 2000 or after 2010
db.movies.find({$or:[{year:{$gt:"2010"}},{year: {$lt:"2000"}}]})
![copyImage](https://github.com/user-attachments/assets/968f846d-7f13-498a-a7c6-b87e38477b8c)
## Update Documents
add a synopsis to "The Hobbit: An Unexpected Journey" : "A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."
db.movies.update({_id:ObjectId("5c9f98e5e5c2dfe9b3729bfe")}, {$set:{synopsis:"A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."}})
![copyImage](https://github.com/user-attachments/assets/1190e8be-0d09-407b-88f9-e4fe23432717)

add a synopsis to "The Hobbit: The Desolation of Smaug" : "The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."
db.movies.update({_id:ObjectId("5c9fa42ae5c2dfe9b3729c03")}, {$set:{synopsis:"The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."}})
![copyImage](https://github.com/user-attachments/assets/b7006279-eb8f-4460-bd65-2212f8c4f214)

add an actor named "Samuel L. Jackson" to the movie "Pulp Fiction"
db.movies.update({_id:ObjectId("5c9f983ce5c2dfe9b3729bfc")}, {$push:{actors:"Samuel L. Jackson"}})
![copyImage](https://github.com/user-attachments/assets/5d1ef9cc-1c86-4694-9609-8c9ebbd51549)

## Text Search
find all movies that have a synopsis that contains the word "Bilbo"
db.movies.find({synopsis:{$regex:"Bilbo"}})
![copyImage](https://github.com/user-attachments/assets/8141d3e3-cfd6-40de-bab8-618e64e07234)


find all movies that have a synopsis that contains the word "Gandalf"
db.movies.find({synopsis:{$regex:"Gandalf"}})

find all movies that have a synopsis that contains the word "Bilbo" and not the word "Gandalf"
db.movies.find({$and:[{synopsis:{$regex:"Bilbo"}}, {synopsis:{$not:/Gandalf/}}]})
![copyImage](https://github.com/user-attachments/assets/26f753ab-275a-4204-bcd8-5c10d064f7fa)

find all movies that have a synopsis that contains the word "dwarves" or "hobbit"
db.movies.find({$or:[{synopsis:{$regex:"dwarves"}}, {synopsis:{$regex:"hobbit"}}]})


find all movies that have a synopsis that contains the word "gold" and "dragon"
db.movies.find({$and:[{synopsis:{$regex:"gold"}}, {synopsis:{$regex:"dragon"}}]})
![copyImage](https://github.com/user-attachments/assets/9ed46d44-3236-4235-b004-489d580c0fcf)

## Delete Documents
delete the movie "Pee Wee Herman's Big Adventure"
db.movies.remove({_id:ObjectId("5c9f992ae5c2dfe9b3729c00")})
![copyImage](https://github.com/user-attachments/assets/06cee791-b9d4-4aec-998e-0bcce193361a)

delete the movie "Avatar"
db.movies.remove({_id:ObjectId("5c9f9936e5c2dfe9b3729c01")})
![copyImage](https://github.com/user-attachments/assets/ea282214-a96b-4bc5-a108-728a1144c154)
