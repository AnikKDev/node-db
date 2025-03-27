# Steps
1. configure aws
2. update the system and install python3-venv
3. set up pulumi project
4. add the vpc, subnets and ec2 instances of db-server and node-server creation codes in __main__.py
5. add a check-mysql.sh script to check db health (to make sure if it is running; if not try to restart with a set amount of interval)
6. create aws key-pair
7. create the vps with `pulumi up` (make sure to run this command from the newly created pulumi project)
8. ssh (check ~/.ssh/config file's content to get the host, user and the identifiters to ssh into each instances)

# Configuration
## configure mysql
1. ssh into it
2. install mysqlserver
3. configure mysql conf file to allow the remote connection (so that it can be accessible from allowed client - in this case for testing purposes we will allow it from everywhere)
4. create user

## configure node server
1. ssh into it from local client
2. add a systemd service here to chek if mysql db server is up and running
3. check systemjournal for the mysql-check service status

# Nodejs application
1. create a directory and set up the nodejs application with `npm init -y` in a `app.js` file
2. read the user with `get` and retrun the response in the app
3. get the db connection status with a `get` api in `/health` endpoint
4. assign the user for the app
5. create a node systemd service for this application
6. keep in mind to check if the nodejs service only runs after mysql sevice is running in the background.
7. run the node systemd service 

# Service flow
![image](https://github.com/user-attachments/assets/9ed4d6e6-f650-445c-bb72-ff48e386030f)
