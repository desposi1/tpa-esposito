## Turner Programming Assessment
## David Esposito
david@espo.coffee
https://github.com/desposi1

#### Problem Statement
We would like you to develop a responsive page that displays twitter feeds. We would like you to show us your cool front-end skills and also your ability to develop a node.js server (HAPI or Express, etc) that uses the Twitter API to get a feed.  This is an opportunity to show us how you develop. We want to see your coding style, use of open source libs, testing approach, documentation, creativity, etc.  You may use any open source libs or available code to support your solution but you must be able to explain your code if you are selected to come in for an in-person interview.  If you have questions, you may send them to me ______ but no immediate responses should be expected.  State any assumptions and move on as the clock for completing the task does not pause.


#### Requirement and Assumptions
* No restrictions on which/how twitter feed is displayed
* Backend must be written in Node.js
* Use front end framework/libraries of choice


#### Features
* Sever
  * Node.js proxy endpoints for anonymous access to user timelines.
  * Node.js proxy endpoints for anonymous access to tweet search functionality.
* Client
  * Single-page React UI
  * Material design using materialcss.com
  * Anonymous access to timeline and search


#### Project Structure
* app
  * conf
    * index.js  // entry point for bootstraping config based on process.env.NODE_ENV
    * dev.js // ... not included in repo since it contains private keys
    * template.js   // skeleton config
  * twitter  // feature modules
    * index.js // feature entry point for bootstrapping
    * endpoints.js   // rest api endpoints with inline documentation
    * twitter.js // Twitter service library for wrapping the twitter api client
  * express-server.js  // entry point for bootstrapping express server
  * index.js   // entry point for application. Loads express and all feature modules.
* ui
  * css
    * main.css
  * ...
  * js
    * index.js   // React application with demo-esque structure
  * index.html
* package.json  // used to manage dependencies/build/run e.g. https://medium.freecodecamp.com/why-i-left-gulp-and-grunt-for-npm-scripts-3d6853dd22b8#.8hidpu0db
* tpaMain.js  // node boot script

Express serves static files from the `/ui` directory from the URL base. The twitter enpoints are located at `/api/twitter/[search, timeline]`

#### Usage

Install:
```
git clone https://github.com/desposi1/tpa-esposito tpa && cd tpa && npm install
```
This repo does *NOT* include my `app/conf/dev.js` config file. To run the server you need to get the file from me
or `cp /app/conf/template.js app/conf/dev.js` and fill out the appropriate values with your own Twitter Application.

Running
```
npm start
```

UI

<http://localhost:3000> or what ever port you used in `/app/conf/dev.js`. Port 3000 is default.

Features:
1. Use the tabs at the top to change tweet source. You can change between User Timeline and Twitter search.
2. Filter the tweet list content by sumitting the tabbed Timeline and Search forms.
  * User Timeline: enter the user's screen name with or without the @.
  * Twitter Search: Enter a query of keywords or constructed using features from https://dev.twitter.com/rest/public/search
3. The tweets are displayed in list view by default but you can use the buttons in the top right to convert the display to a tile grid layout.
4. The UI is responsive with 3 break points @ small, medium, and large.


#### Lacking / TODO
1. Server / client testing
2. Server error handling and appropriate rest api error responses
3. Client side build process
  * dependency management
  * transpiling
  * script concatenation
  * minification
  * uglify
4. Tweet entity handling/markup
  * @mentions
  * embedded media
  * links
5. Reactive bugs
  * overflow
  * layout buttons only register onClick when icon is clicked.
6. ES6 support server side.

#### Special Notes
I like bootstrap's styling and component library much better than MaterializeCSS.
