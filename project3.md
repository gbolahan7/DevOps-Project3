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


## MONGODB DATABASE
### MongoDB will be made use of in this app as its a NoSQL db.  First, sign up to set up an account and then create a db. Then, a url connection string to connect to the app will be generated with already created username, password and db name set for the database created.

### Create an env file in the ToDo directory and then insert db connection details
`touch env`
`vi .env`

`DB = 'mongodb+srv://<username>:<password>@<network-address>/<dbname>?retryWrites=true&w=majority'`

### Next is to update the index.js file to use the environment variable created so as to connect to the db
![index upd](/images/index-update.PNG)

### start server
`node index.js`
![db conn](/images/db-conn.PNG)

## Test the backend code using RestAPI
### Postman application is used to implemnent the endpoint tests
![api test1](/images/api-getReq.PNG)
![api test2](/images/api-delete.PNG)


# STEP 2 - FRONT END 
### Use creat-react-app to scaffold the app with the client folder created
` npx create-react-app client`

### Running the app, install the following:
`npm install concurrently --save-dev`
`npm install nodemon --save-dev`

### update the package.json file scripts so as to be able to use the concurrently package installed


`"scripts": {`
`"start": "node index.js",`
`"start-watch": "nodemon index.js",`
`"dev": "concurrently \"npm run start-watch\" ``\"cd client && npm start\""`
`}`

### Change directory to client folder and update the package.json file with a proxy url config.
`"proxy": "http://localhost:5000"`
### This is to be able to run the backend and the front end at the same time. To make this happen, run this command: npm run dev
### NB: Port 3000 needs to be opened on the EC2 instance since the app is running on the port
![npm run](/images/npm-rundev.PNG)
![npm run](/images/frontend.PNG)

### Next, create components folder in the src directory and create 3 files: Input.js, ListTodo.js and Todo.js and paste code into the files respectively.
![todoList](/images/todoList-code.PNG)

![todo](/images/todo-codee.PNG)


### Install AXIOS which is HTTP client for browser and node
`npm install axios `

### Update the following files with code: app.js, app.css and index.css
`vim app.js`
`vim app.css`
`vim index.css`

![appjs code](/images/appjs-code.PNG)

![appcss code](/images/appcss-code.PNG)

![indexcss code](/images/indexcss-code.PNG)


### Change directory to the Todo root folder and run the command:
`npm run dev`

![todoapp1](/images/todoapp-web.PNG)

![todoapp2](/images/todoapp-webapp.PNG)


## A ToDo application created and deployed to MERN stack with ReactJS for frontend and ExpressJS for backend.