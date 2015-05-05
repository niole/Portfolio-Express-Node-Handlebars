# Portfolio-Express-Node-Handlebars
A simple backend created with the goal of portfolio creation in mind.

## First, clone github repo. Below are some specifics that may come in handy...

## The File Tree
- views
  - layouts
  - partials
- routes
- public
  - js
  - css
  - images
- bin
  
  If we want to use images in our portfolios, we can store them in `/images` and go from there.

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

* next, we'll look at how we set up the handlebars templating

## Handlebars templating

  * We will need to create a `single.hbrs` file in `/views/layouts` containing:
  
      ```javascript
        <html>
          {{>head}}
           <body>
            <div class="container">
              <div class="row">
                <div class="col-md-12 text-center">
                    {{{ body }}}
                </div>
              </div>
            </div>
          </body>
        </html>
    ```
  * Next create `/views/partials/head.hbs`, which will contain everything that you would put in the `head` of your html file: links to cdns, scripts, et c..
