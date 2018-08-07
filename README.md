## Summary 
Commandline Cheatsheet for various command line commands that can be complex, but are used often enough you need to copy and paste.

# Commands

##### delete all LOCAL branches except master: 
###### (not recommended)
`git branch | grep -v "master" | xargs git branch -D`

## Database Management

##### import compressed database
`zcat database.sql.gz | mysql -u username databasename`

##### import MySQL database
`mysql -u root database_name < file.sql`

##### import compressed MySQL database
`zcat file.sql.gz | mysql -uroot database_name`

##### check SQL database size during an import
`
SELECT table_schema "database_name", sum( data_length + index_length ) / 1024 / 1024 "DataBase Size in MB" 
   FROM information_schema.TABLES GROUP BY table_schema;` 

##### mysqldump to compressed file 

`mysqldump -u username -p  databasename | gzip > newfilename.sql.gz`

## Server file transferring 

##### move files from LOCAL to SERVER
`scp /dir/on/local/with/file.here avaughan@servername.com:/path/on/server/to/place/file`

##### move files from SERVER to LOCAL
`scp username@sitedomain.com:/file/directory.here /home/alexander/place/file/here`

## Miscellaneous

##### view server info
`dig @8.8.8.8 domain.name.org`

##### get jks key sha1
`keytool -exportcert -list -alias aliasnamehere -keystore "directory/where/your/keystore/here.jks" -storepass storepasshere -keypass keypasshere
`
##### Other cheatsheets
* https://gist.github.com/hofmannsven/8392477
