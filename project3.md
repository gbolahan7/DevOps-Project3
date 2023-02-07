# SIMPLE TO-DO APPLICATION ON MERN WEB STACK

## STEP 1 - BACKEND CONFIGURATION

### Update Ubuntu
`$ sudo apt update`

### Upgrade Ubuntu
`$ sudo apt upgrade`

### Install NodeJS
`$ sudo apt-get install -y nodejs`

### Verify Node Installation
`node -v`
![node install](/images/node-install.PNG)

### Application Code Setup
`mkdir Todo`

### Change directory to the new created directory and initialize it
`cd todo`
`npm init`
![npm init](/images/npm-init.PNG)

## - INSTALL EXPRESSJS
`npm install express`

### create a file 
`touch index.js`

### Install the dotenv module and open the index.js 
`npm install dotenv`
`vim index.js`

### paste code inside 
![npm init](/images/vim-index.PNG)

### now enter ctrl+c and then :wq

### Start server
`node index.js`
![npm init](/images/port5000.PNG)

### Open port 5000 on the EC2 instance security group by editing the inbound rule and adding a custom TCP port 5000.

### Open browser and access the server's public IP with the port 5000
`http://<PublicIP-or-PublicDNS>:5000`
![npm init](/images/express-web.PNG)

### The following are the expected actions from the Todo app with each task associated with an enpoint (POST, GET, DELETE) method:
### 1 Create a new task
### 2 Display list of all tasks
### 3 Delete a completed task


## Create routes for each task
`mkdir routes`
`cd routes`

### create a file and ioen the file
`touch api.js`
`vim api.js`
![api code](/images/api-code.PNG)

## CREATE MODELS
### Install Mongoose and create a folder for Models
`npm install mongoose`
`mkdir models`

### Change directory to the Models folder and create a file in it
`cd models` 
`touch todo.js`

### paste code 
![mongoose code](/images/mongoose-code.PNG)

### Update the api.js code in routes directory
![api codeupdt](/images/api-update.PNG)
