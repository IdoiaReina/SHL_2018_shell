# SHL_2018_shell
Epitech's Shell/database program made with Cynthia Bon


### Description: 
  Shell script that allows you to manage a database in a json file.
  You can create table, insert-update-remove data, run query, ...
		 
Database File:
  The database file can be specified in 3 ways, in order of priority:
	  as argument in command line : -f file
    in environment : BDSH_File=
    in a configuration file : .bdshrc
	
### Usage :

```
./bdsh [OPTION]... [COMMAND] [REQUEST]
```
OPTION:
  -h				display usage
  -f FILE		json database file
  -j        json formated output for select command

COMMAND and REQUEST:
create : create database

```
./bdsh -f file.json create database
./bdsh -f file.json create table user id,firstname,lastname
./bdsh -f file.json create table age id,age
```

insert: insert data in database
 
```
./bdsh -f file.json insert user id=1,firstname=John,lastname=SMITH
./bdsh -f file.json insert user id=4,firstname=Robert\ John,lastname=WILLIAMS
./bdsh -f file.json insert user id=2,firstname=Lisa,lastname=SIMPSON
./bdsh -f file.json insert user id=10,lastname=SMITH
./bdsh -f file.json insert user firstname=Laura,lastname=SMITH
./bdsh -f file.json insert user id=9
./bdsh -f file.json insert age id=1,age=42
```
      
describe: describe table structure

```
./bdsh -f file.json describe user
id
firstname
lastname
```
  
select: display data from database

```
./bdsh -f file.json select user firstname,lastname
firstname    | lastname
-------------------------
John         | SMITH
Robert John  | WILLIAMS
Lisa         | SIMPSON
             | SMITH
Laura        | SMITH
             |

./bdsh -f file.json select user lastname,firstname order
lastname  | firstname
-------------------------
          |
SIMPSON   | Lisa
SMITH     |
SMITH     | John
SMITH     | Laura
WILLIAMS  | Robert John
