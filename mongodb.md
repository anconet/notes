# MongoDb
[← Return to Home](readMe.md)
---
## Instructions for Messing with the Mongodb on disk.
Assuming you have done a volume map from the mongodocker 

Ways to get in:
```bash
// Running the daemon 
mongod --dbpath /path/to/your/data/db
# Accessing inside a running container
sudo docker exec -it <container> bash
mongosh --username <userName> --password <password> --authenticationDatabase admin
show dbs
use schedulera # to switch to the correct database
show collections
# Get a JSON array of collections
db.getCollectionNames()
```
Pulling a list of all collections with mongosh:
```bash
mongosh --username <userName> --password <password> --authenticationDatabase admin \
--eval "db.getCollectionNames()" db
```
In the mongoDb Shell:
```bash
mongo
show dbs
use <your_database>
db.<your_collection>.find().pretty()
```
To export
```bash
mongoexport --db mydb --collection users --out users.json --jsonArray
```