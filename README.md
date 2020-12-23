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

### Hotreloading

installed nodeman as developer dependency to enable server reloading when file is changed.
```sh
$ npm install --save-dev nodemon
```
To allow for greater flexibility, a seperate start script was added to the package.json.

## Eslint

### Exceptions

Default gitignore file used to ignore project dependencies (node_moddules)

