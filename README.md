# Portfolio-Express-Node-Handlebars
A simple backend created with the goal of portfolio creation in mind.

## Create File Tree
- views
- routes
- public
  - js
  - css
  - images
- bin

## Create top level files

* create `package.json`. run `npm init`, hit enter until all options exhausted. Then run in terminal:
 
  ```sh
  npm install --save express;
  npm install --save serve-favicon;
  npm install --save morgan;
  npm install --save cookie-parser;
  npm install --save body-parser;
  npm install --save debug;
  npm install --save express-handlebars;
  npm install --save mongodb;
  npm install --save mongoskin;
  npm install --save dotenv;
  ```
* create `app.js` and copy and paste the contents of `app.js` created for this repository.
  The following code specifies that this app will use handlebars templating:

```javascript
var exphbs = require('express-handlebars');
app.engine('.hbs', exphbs({defaultLayout: 'single', extname: '.hbs'}));
app.set('view engine', '.hbs');
```

* next, we'll set up the `/routes/index.js`. Create the file and add the following code:

    ```javascript
    #!/usr/bin/env node
    var debug = require('debug')('my-application');
    var app = require('../app');
     
    app.set('port', process.env.PORT || 3000);
       
    var server = app.listen(app.get('port'), function() {
    debug('Express server listening on port ' + server.address().port);
    });
     ```
