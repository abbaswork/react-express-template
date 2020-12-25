# Client Setup

## Framework

### React

React App setup with:
```sh
npx create-react-app client
```
The [create-react-app](https://github.com/facebook/create-react-app) package comes preconfigured with webpack and babel along with:
- React, JSX, ES6, Typescript and flow syntax support
- Autoprefixed css (don't need webkit)
- Built in unit tester
- Live development server 
- Basic scripts to build and run the app
- service worker and web app manifest
- easy updates with single dependancy
- along with a simple starting directory structure and starter package.json

## Dev Dependencies

### Source Map Explorer

Source map explorer analyzes JavaScript bundles using the source maps. This helps you understand where code bloat is coming from.
```sh
npm install --save source-map-explorer
```

To analyze for bloat an "analyze" script was setup in package.json

### Sass

Sass is a CSS preprocessor, installed as a developer dependency with
```sh
npm install node-sass --save
```

## Project Structure

Folder structure uses default create-react-app structure, inside of src files, folder structure is organised by feature type.

- public: static assets
- src: js files
    - assets: css, scss files
    - configure: configure variables such as Redux stores
    - constants: such as action-types
    - util: utility functions
    - common: example folder to hold common components
    - profile: example feature folder that would contain profile components and related files


# Server Setup

## Framework

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

Manually added middleware:
- [Cors](https://www.npmjs.com/package/cors): configure cors in express


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

## Project Structure

The project structure uses CommonJs along with the 3 layer architecture for effective seperation of concerns, where the layers are:
1. Controller (routes): contains route controllers
2. Service Layer (services): Bussiness logic seperated from controller and Data Acess logic.
3. Data Access Layer (models):  Database logic and models

where the folders would be:

- bin: server entry point, www introduced in express 4 to maintaine middleware independently
- routes: route controllers for all the endpoints in the app
- public: js, css and image files
- views: view template (express)
- config: env variables and config files
- jobs: jobs to be carried out by workers
- loaders: splitting up startup proces into modules (Express, PSQL, Sequelize, Redis, etc. connections)
- models: Database models
- services: Bussiness logic

