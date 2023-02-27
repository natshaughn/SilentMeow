# Pets Database
Develop SQL statements required to manipulate a database of pets<br>

[data types](https://www.w3schools.com/sql/sql_datatypes.asp),
[hsqldb](http://hsqldb.org/),
[sql](https://www.w3schools.com/sql/),
[uuid](https://www.uuidgenerator.net/)

## Pre-requirements
* Ensure the Eclipse IDE has Maven by looking for M2E from Help About ([details](https://www.vogella.com/tutorials/EclipseMaven/article.html))
* Install `DBViewer Plugin 1.2.2.v20101009` by ZIGEN from the Eclipse IDE marketplace
* Import into Eclipse as Git with smart import (accepting all defaults in wizard)
* Let the IDE finish building dependencies before proceeding (see bottom right of Eclipse)

## Steps
* Run the PetsDB app to start the database
* Develop Pets-based SQL statements
* Switch to DBViewer perspective to test
* Stop the PetsDB app to shutdown database
* Ensure SQL documented within this README
* Push update README back to forked GitHub

## Bonus
* Create another related table with SQL

## Database Schema

**Animal table**
 - Hunger INT
 - Id CHAR(36)
 - Name VARCHAR(100)
 - OwnerId CHAR(36)
 - Species CHAR(1)

**Owner table**
 - Id CHAR(36)
 - Name VARCHAR(100)
 - Town VARCHAR(100)
 
**To create the Owner table**<br>
`TODO`

**To create the Animal table**<br>
`TODO`

**To insert a new Owner row**<br>
`TODO`

**To insert a new Cat row**<br>
`TODO`

**To insert a new Dog row**<br>
`TODO`

**To query an animal**<br>
`TODO`

**To query all pets for an owner**<br>
`TODO`

SQL Commands
CREATE TABLE Ownerz (Id CHAR(36), Name VARCHAR(100), Town VARCHAR(100), PRIMARY KEY(Id))

SELECT * FROM Ownerz


INSERT INTO Ownerz (id, Name, Town) VALUES ('050650b3-85b0-4925-9b4b-952fb4058450', 'Nathan', 'Rossendale')
INSERT INTO Ownerz (id, Name, Town) VALUES ('488ee53e-7838-4435-9063-816cf1432223', 'Tommy', 'Manchester')
INSERT INTO Ownerz (id, Name, Town) VALUES ('bd96092f-dce4-4bde-be15-d5df29c3c296', 'Jo', 'Preston')
INSERT INTO Ownerz (id, Name, Town) VALUES ('179faaf5-fefb-43ab-8e1f-17a90f1bc308', 'Cat', 'Blackburn')
INSERT INTO Ownerz (id, Name, Town) VALUES ('9a8c7e0a-e2e8-4952-b7f8-3026924f4457', 'Tom', 'Leeds')

SELECT * FROM Ownerz

CREATE TABLE Animalz (Hunger INT, Id CHAR(36), Name VARCHAR(100), OwnerId CHAR(36), Species CHAR(1), PRIMARY KEY(Id), FOREIGN KEY (OwnerId) REFERENCES Ownerz(Id))



INSERT INTO Animalz (Hunger, Id, Name, OwnerId, Species) VALUES (100, 'abca68ef-6549-4230-b57a-5ac5f1afe100', 'Bobby', '050650b3-85b0-4925-9b4b-952fb4058450', 'D')
INSERT INTO Animalz (Hunger, Id, Name, OwnerId, Species) VALUES (90, 'a173c48e-21cf-4835-ad7f-b449020e3508', 'Tia', '179faaf5-fefb-43ab-8e1f-17a90f1bc308', 'D')
INSERT INTO Animalz (Hunger, Id, Name, OwnerId, Species) VALUES (80, 'dcf0d132-afd1-4865-9161-7bc54d8e49df', 'Albus', '488ee53e-7838-4435-9063-816cf1432223', 'C')
INSERT INTO Animalz (Hunger, Id, Name, OwnerId, Species) VALUES (70, 'b52f52c1-889b-45f2-acd8-7fcc7677eb81', 'Tess', '9a8c7e0a-e2e8-4952-b7f8-3026924f4457', 'D')
INSERT INTO Animalz (Hunger, Id, Name, OwnerId, Species) VALUES (1, '778896d7-5647-4c15-8d6f-16abd7c9cd36', 'Ozzy', 'bd96092f-dce4-4bde-be15-d5df29c3c296', 'P')

INSERT INTO Animalz (Hunger, Id, Name, OwnerId, Species) VALUES (100, 'd3a571c8-8f5a-4471-8c92-383f7d6042cd', 'Bob', '050650b3-85b0-4925-9b4b-952fb4058450', 'D')

SELECT * FROM Animalz

SELECT * FROM Animalz WHERE OwnerId = '050650b3-85b0-4925-9b4b-952fb4058450'

SELECT animalz.Hunger FROM Ownerz Ownerz, Animalz animalz WHERE ownerz.Name = 'Nathan' AND animalz.OwnerId = ownerz.Id 
