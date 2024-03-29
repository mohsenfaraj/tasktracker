# Task Tracker Dockerized!

> by mohsen farajollahi , 991152143

this is a fullstack simple todo app written with MERN stack (Mongodb , Express , React , Nodejs).
this project is dockerized and can deployed anywhere with docker installed.
this project may look easy but i had nightmares in authentication, dockerizing react app (special thanks for Vite!) and setting CORS.
this project still needs security implementations (mongodb authentication and etc.) therefore its just for educational use only.

## how to install

- pull this repository by this command:

> for ssh:

```bash
git clone git@gitlab.com:gmohsenfarajollahi/tasktracker.git
```

> for https:

```bash
git clone https://gitlab.com/gmohsenfarajollahi/tasktracker.git
```

- open the project directory with cd command:

```bash
cd ./tasktracker
```

- run docker compose

```bash
docker compose up
```

and you are ready to go! you can add `-d` to end of command for de-attached mode.

if you want to stop all of the containers do as follow:

- open the project directory in terminal and enter this command:

```bash
docker down
```

if you want to also remove the database you can add `--volumes` flag to end of command above.

if you made any changes to `api` or `front` folder you should re-build the images using:

```bash
docker build
```

- mongodb server will run on http://localhost:27017
- application's backend (api) will run on http://localhost:3000
- application's frontend (react) will run on http://localhost:8080

you can change the default ports from **.env** file.

## API routes

if you use [thunder client](https://www.thunderclient.com/) a REST API client extension for vs code, you can import the collections from `collection.js` file.

- `/register` [post]
  params: username , password
  sign up a new user
- `/login` [post]
  params: username , password
  log in as existing user
- `/logout` [get]
  logs out from account
- `/add` [post]
  params: name , done
  add a new task
- `/remove` [post]
  params: id
  removes a task
- `/update` [post]
  params: id , name , done
  updates an existing task
- `/` [get]
  gets all tasks related to that user

## .env sample file

```
MONGODB_PORT=27017
MONGO_DATABASE=test
NODE_ENV=production
PORT=3000
MONGO_URI=mongodb://mongodb:${MONGODB_PORT}/${MONGO_DATABASE}
FRONT_URL=http://localhost:8080
VITE_API_URL=htto://localhost:3000
```
