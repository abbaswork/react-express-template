# react-express-template

## Server Setup

### Express

Express was setup using the express generator via the command:
```sh
$ express react-express-template
```

The [express generator](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/skeleton_website) sets up a skeleton server with:
 - Simple starting directory structure with an ./bin/www entry point
 - Express application object called app with basic middleware (see packages), routes and view setup
 - View template (in this case Jade)
 - Starter package.json with start script and the following packages
    - [cookie-parser](https://www.npmjs.com/package/cookie-parser): cookies
    - [debug](https://www.npmjs.com/package/debug): debugging
    - [morgan](https://www.npmjs.com/package/morgan): logging
    - [http-errors](https://www.npmjs.com/package/http-errors): send http errors


## Dev Dependencies

These are installed as dependencies only used during development.

### Hotreloading

Installed nodeman as developer dependency to enable server reloading when file is changed.
```sh
$ npm install --save-dev nodemon
```
To allow for greater flexibility, a seperate "devstart" script is added to the package.json.

### Eslint

Installed eslint as developer dependency to perfome static analysis and report non-adherance code.
```sh
npm install eslint --save-dev
```
A seperate "lint" script is added to the package.json to check js files. The eslint is setup so adhere to the standard js styling guide and installed via
```sh
eslint --init
```
### Exceptions

Default gitignore file used to ignore project dependencies (node_moddules)

## Project Structure

The project structure uses CommonJs along with the 3 layer architecture for effective seperation of concerns, where the layers are:
1. Controller (routes): contains route controllers
2. Service Layer (services): Bussiness logic seperated from controller and Data Acess logic.
3. Data Access Layer (models):  Database logic and models

where the folders would be:

- bin       # app entry point using app.js
- routes    # route controllers for all the endpoints in the app
- public    # js, css and image files
- views     # view template (express)
- config    # env variables and config files
- jobs      # jobs to be carried out by workers
- loaders   # splitting up startup proces into modules (DB, ORM, Redis, etc connections)
- models    # Database models
- services  # Bussiness logic

