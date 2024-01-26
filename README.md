# SmartBrain-api - v1
Final project for ZTM course

1. Clone this repo
2. Run `npm install`
3. Run `npm start`
4. Enter the details for your own databse in `server.js`

** Make sure you use postgreSQL instead of mySQL for this code base.

POSTGRES
--------

- psql -U postgres
Password for user postgres: ****
current version - psql (16.1)

To create a new database 
---------------------------

- createdb -U postgres test

(-U indicates use of postgres, test is name of database)

- psql -U postgres test

(it will come to database test)

- CREATE TABLE users (id SERIAL PRIMARY KEY, name VARCHAR(255), email VARCHAR(255));

(it will create a table users with col id, name and email)

- \dt

(use to display users table)

- INSERT INTO users (name, email) VALUES ('john', 'john@doe.com');

(it will insert into users table)

- SELECT * FROM users;

(display all data from users table);

-------------------------------------------------------

We can do the same thing with pgAdmin

- search pgAdmin and open it by entering your password
- Go to db -> schemas -> table -> add or update data -> save
- We can also use query tool in PGadmin 4 -> Right click -> veiw query tool -> run command.

-------------------------------------------------------

Smart-Brain Setup
------------------

- Create smart-brain database

createdb -U postgres smart-brain

- Connect with smart-brain

psql -U postgres smart-brain

- Create users table

CREATE TABLE users (
	id serial PRIMARY KEY,
	name VARCHAR(100),
	email text UNIQUE NOT NULL,
	entries BIGINT DEFAULT 0,
	joined TIMESTAMP NOT NULL
);

- Create login table 

CREATE TABLE login (
	id serial PRIMARY KEY,
	hash varchar(100) NOT NULL,
	email text UNIQUE NOT NULL
);

-------------------------------------------------------

Connect to db
---------------

- using KNEX.JS library
- Installation -> npm install knex
- Install db also -> npm install pg
- Initialize the library
- to see the relation -> \d



https://smartbrainapi-re5w.onrender.com