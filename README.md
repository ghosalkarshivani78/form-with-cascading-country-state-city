# form-with-cascading-country-state-city
form with cascading country state city
SELECT * FROM test.userstate;

create database usercascad
use usercascad
create table empstate(
 id int NOT NULL AUTO_INCREMENT,
    firstname varchar(255) NOT NULL,
    lastname varchar(255) NOT NULL,
	email varchar(255) NOT NULL,
    address varchar(255) NOT NULL,
	countryid int not null,
	stateid int not null,
    cityid int NOT NULL,
	number varchar(200) not null,
    PRIMARY KEY (id),
FOREIGN KEY (stateid) REFERENCES states1(stateid),
FOREIGN KEY (cityid) REFERENCES city1(cityid),
FOREIGN KEY (countryid) REFERENCES country(countryid)
)


create table country
(
 countryid int NOT NULL AUTO_INCREMENT,
countryname varchar(200) not null,
 PRIMARY KEY (countryid)
)

create table states1
(
 stateid int NOT NULL AUTO_INCREMENT,
statename varchar(200) not null,
countryid int NOT NULL,
PRIMARY KEY (stateid),
FOREIGN KEY (countryid) REFERENCES country(countryid)
)

create table city2
(
cityid int NOT NULL AUTO_INCREMENT,
cityname varchar(255) NOT NULL,
stateid int not null,
 PRIMARY KEY (cityid),
FOREIGN KEY (stateid) REFERENCES states1(stateid)
)
