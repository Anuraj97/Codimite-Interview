# Getting Started with Create React App

### First move to the client folder
cd client

### Install the dependencies
npm i

### Need to execute below command 
npm run build

### In the project directory, you can run:
 `npm start`

Runs the app in the development mode
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

### Open XAAMP and start the Apache and MySQL server. Then go to phpmyadmin console and create database named as 'todolist'
### Create table as todos
### Create two columns 
name -> id, type-> int, size->as prefer, auto-increment->true
name -> todo, type-> varchar -> size->as prefer


### Open another terminal and execute to server folder
cd server

### Install the dependencies
npm i

### Need to execute below command 
npm run build

### In the project directory, you can run:
 `npm start`

You can:

- add tasks,
- edit tasks,
- delete tasks

### Technologies

Project is created with:

Backend:

- Node
- Express
- MySQL

Frontend:

- React
- Bootstrap 5

### Create the terraform file for spin up Ec2 and RDS MySQL instance
### To Spin up the Instance execute below commands

terraform init
terraform plan
terraform apply

Reason for use AWS for deploy the application

Previously I had a free tire GCP and that one expired. I tried to create new free tire account bu the card details weren't taken to
create new fire tire account. After that I tried with my previous account again but for access many services had to create budget plan or something.
That one also i was unable to create because the card details couldn't apply for that.

### Then create the connection between RDS and Ec2

Login Ec2 instance using aws shell and execute below commands

sudo yum -y update

For mariadb installation
sudo yum instal -y mariadb-server
sudo systemctl enable mariadb
sudo systemctl start maridb

To connect to the MySQL execute below command and then after proveide the password.
mysql -h [end point of RDS] -P 3306 -u [database name] -p

And by using created database, create a table named as todos
create the column as below
column name      Type     size   auto_increment
id                INT      100      true
todo              Varchar   200      -

### Deploy the application in Ec2

Follow the commands

sudo su 

Install the node js in Ec2 
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
. ~/.nvm/nvm.sh
nvm install 16
node -e "console.log('Running Node.js ' + process.version)"

For more details follow the link - https://docs.aws.amazon.com/sdk-for-javascript/v2/developer-guide/setting-up-node-on-ec2-instance.html

Install Git 
yum install git

Install serve globle
npm install serve -glboal

Navigate to created directry
cd workspace

clone the repository
git clone https://github.com/Anuraj97/Interview.git

Go to the security group and add rule as below
Type           Protocol    port
HTTP             TCP        80
Custom TCP       TCP       3000

Navigate to client directory and execute below commands
npm install
npm run build
serve -s build

Then go to Ec2 instance and access the public IP with port 3000


Navigate to server directory and execute below commands
npm install

Navigate to the server/util/db.js file and change host as RDS database endpoint

npm start


