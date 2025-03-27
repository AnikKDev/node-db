# Steps
1. configure aws
2. update the system and install python3-venv
3. set up pulumi project
4. add the vpc, subnets and ec2 instances of db-server and node-server creation codes in __main__.py
5. add a check-mysql.sh script to check db health (to make sure if it is running; if not try to restart with a set amount of interval)
6. create aws key-pair
7. create the vps with `pulumi up` (make sure to run this command from the newly created pulumi project)
8. ssh (check ~/.ssh/config file's content to get the host, user and the identifiters to ssh into each instances)
9. 
