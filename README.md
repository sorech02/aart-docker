# aart-docker
## Get a copy of aart.war
* Download from here: https://github.com/immregistries-internal/aart-measure/releases/download/v2.43.6/aart-docker.war
  * OR Build AART with the connections changed like here: https://github.com/immregistries-internal/aart-measure/commit/dfb2df0f9bee2c17495f96839d7e03752bb39986
* Name the file aart.war and place at the root level with docker-compose.yml

## Get the database set up
* Get an export sql file by some means
* Append the following to the export, with the real password inserted:
```
CREATE USER 'aart_web'@'%' IDENTIFIED WITH mysql_native_password BY 'PUT_PASSWORD_HERE';
GRANT ALL ON aart.* TO 'aart_web'@'%';
```
* Place the .sql file in the mysql-init directory

## Run
* `docker-compose up` in the root directory
* AART will run at http://localhost:8080/aart/home

# Open Issues
* Customize Tomcat to address issues like https://github.com/immregistries-internal/AART/issues/1761
* Link file location for iz-profiles, currently they will look for c:\dev\iz-profiles , which doesn't exist. 
