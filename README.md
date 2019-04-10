**Starting node-server:**

1. Import donorapp.sql into MySQL server. If needed, find the following lines in your app.js and modify it as per your configuration.

   ```js
   app.use(function(req, res, next) {
     res.locals.connection = mysql.createConnection({
       host     : 'your_host',
       user     : 'your_root',
       database : 'your_database_name',
       password: "your_password_here"
     });
     res.locals.connection.connect();
     next();
   });
   ```

2. Do `npm install` - This will install all the dependencies listed in the package.json.
3. `node app.js` will start the server on localhost:4000

**Starting the react application:**

1. From the root directory, go to client folder. Do `npm install` in the client folder.
2. Do `npm start` and the client will be started at localhost:3000. The proxy is already configured to make all the requests to localhost:4000.
