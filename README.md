# skill-tree-backend

## Steps for running the service in local
_A detailed README is written by @shubham sidgar, this is written temporarily for people to get their backend running, more details in this ticket #25_


### Tools required
- [Maven](https://mvnrepository.com/)
- Java
- IDE
- Docker desktop
- Mysql docker image

### Steps for connecting the service to the Mysql running in docker
This [link](https://find10archived.medium.com/how-to-connect-a-mysql-docker-container-with-a-local-spring-boot-application-9366707dce0d) can be used as reference for the steps
- Create a database user with all access to create tables, delete and drop tables [This is for development only in local MySql]
- After creating the database user, enter the credentials in the Skill tree spring boot application
- Try connecting the database on this URL = "jdbc:mysql://${MYSQL_HOST:localhost}:3306/${DB_NAME}"
- Try writing a simple API to test out the database connection and the data retrival

### Steps to generate a JWT token same as our [website-backend repo](https://github.com/Real-Dev-Squad/website-backend/issues)
- To generate the JWT token, we need to have the website-backend running locally.
- Have a user token (private and public key stored in `local.js` file)
- Post calling the `localhost:3000/auth/github/login`, backend will generate the JWT token
- We can validate if the token is correct using the site https://jwt.io/, enter the public and private key stored in the website backend
- Post this use the public key in Skill tree repo to decrpyt the JWT token passed for the auth.
