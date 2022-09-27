# __Setting for Node.js & Express.js__
<br>

### __npm init & install express__
</br>

1. node version check
    - node -v
2. npm init(create package.json)
    - npm init
3. Install express(create node_modules, package-lock.json)
4. Install babel, nodemon

    ``` javascript
    //server.js
    const express = require('express');
    const app = express();

    app.get('/', function(req, res){
        res.send('Home');
    });
    export default app;
    ```
    ``` javascript
    //init.js
    import app from "./server";

    const HOST = process.env.HOST || "0.0.0.0";
    const PORT_NO = process.env.PORT || 11080;
    const LISTEN_LOG = `Waiting on port ${HOST}:${PORT_NO}`;

    app.listen(PORT_NO, HOST, LISTEN_LOG, () => {
        console.log(LISTEN_LOG);
    });
    ```
</br>


### __Dependencies__
</br></br>

+ __express__
    - role: web framework for Node.js
    - install: ```npm install --save express```
    - config: node_modules, package-lock.json
    - usecase:
        ``` js
        // server.js
        //To understand the Form-Data.
        app.use(express.urlencoded({extended: true}));
        //To understand text messages.
        app.use(express.json());
        ```
</br></br>

+ __babel__
    - role: helps you to write code in the latest version of Javascript.
    - install: ```npm install --save-dev @babel/cli @babel/node @babel/core @babel/preset-env```
    - usecase:
        ``` json
        //babel.config.json
        {
            "presets": ["@babel/preset-env"]
        }
        ```

+ __nodemon__
    - role: automatically restart the node application when file changes
    - install: ```npm i --save-dev nodemon```
    - usecase:
        ``` json
        //package.json
        "scripts":{
            "dev:server": "nodemon"
        }
        ```
        ``` json
        //nodemon.json
        {
            "ignore": ["webpack.config.js", "src/client/*", "assets/*"],
            "exec": "babel-node server/init.js"
        }
        ```

+ __dotenv__
    - role: .env reader
    - install: ```npm i dotenv --save```
    - usecase:
        ```     
        //.env 
        ID=soapunny
        PASSWORD=1234
        ```
        ``` javascript
        //js
        import * as dotenv from 'dotenv'

        const ID = process.env.ID;
        const PASSWORD = process.env.PASSWORD;
        ```

+ __morgan__
    - role: HTTP request logger middleware for node.js
    - install: ```npm i morgan```
    - usecase:
        ``` javascript
        //server.js
        const morgan = require('morgan');
        ```

+ __express-session__
    - role: Create a session middleware with the given options.
    - install: ```npm i express-session```
    - usecase:
        ``` js
        //server.js
        app.set('trust proxy', 1); //trust first proxy
        app.use(session({
            secret: process.env.COOKIE_SECRET,
            resave: false,
            saveUnintialized: true,
            cookie: {
                secure: true,
                maxAge: 1000 * 60 * 30, // millisec, total: 30 mins
            }
        }));
        ```
+ __mongoose__
    - role: MongoDB object modeling tool designed to work in an asynchronous environment. Mongoose supports both promises and callbacks.
    - install: ```npm i mongoose```
    - usecase:
        ``` js
        //db.js
        import mongoose from "mongoose";

        mongoose.connect(process.env.MONGO_DB_URL);
        const db = mongoose.connection;
        db.on("error", (error) => console.log("DB Error: ", error));//on : everytime
        db.once("open", () => console.log("Connected to DB!"));//once: one time
        ```

+ __pug__
    - role: high-performance template engine implemented with Javascript for Node.js and browsers.
    - install: ```npm i pug-cli g```
    - usecase:
        ``` js
        //server.js
        app.set("view engine", "pug");
        app.set("views", process.cwd() + "/src/views"); //Change process's current directory.
        ```
+ __express-flash__
    - role: Flash is an extension of connect-flash with the ability to define a flash message and render it without redirecting the request.
    - install: ```npm i express-flash```
    - usecase:
        ``` js
        //server.js
        import flash from "express-flash";
        app.use(flash());
        ```
+ __webpack__
    - role: Webpack is a bundler for modules. The main purpose is to bundle Javascript files for usage in a browser.
    - install: ```npm i --save-dev webpack```
    - usecase:
        ``` js
        //webpack.config.js
        const path = require("path");
        const MiniCssExtractPlugin = require("mini-css-extract-plugin");

        const BASE_JS_ROOT = "./src/client/js/";

        //path.resolve(__dirname, "assets", "js") => add up the paths together.
        module.exports = {
            entry: {
                main: `${BASE_JS_ROOT}main.js`,
                videoPlayer: `${BASE_JS_ROOT}videoPlayer.js`,
            },
            plugins: [new MiniCssExtractPlugin({
                filename: "css/styles.css",
            })],
            output: {
                filename: "js/[name].js",
                path: path.resolve(__dirname, "assets"),
                clean: true,
            },
            module: {
                rules: [
                    {
                        test: /\.m?js$/,
                        exclude: /node_modules/,
                        use: {
                        loader: 'babel-loader',
                        options: {
                            presets: [
                            ['@babel/preset-env', { targets: "defaults" }]
                            ],
                        },
                        },
                    },
                    {
                        test: /\.s[ac]ss$/i,
                        use: [
                            // Creates `style` nodes from JS strings
                            MiniCssExtractPlugin.loader,
                            // Translates CSS into CommonJS
                            "css-loader",
                            // Compiles Sass to CSS
                            "sass-loader",//webpack starts from the back
                        ],
                    },
                ],
            },
        };
        ```
+ __MiniCssExtractPlugin__
    - role: This plugin extracts CSS into separate files. It creates a CSS file per JS file which contains CSS. It supports On-Demand-Loading of CSS and SourceMaps.
    - install: ```npm install --save-dev mini-css-extract-plugin```
    - usecase:
        ``` js
        // In the webpack usecase.
        ```
</br>


### __CORS(Cross-Origin Resource Sharing) & SOP(Same-Origin Policy)__
</br>

+ Why do we use it?
    - Enhance security by specifying restrictions on resources coming from other sources.
    - 다른 출처에서 오는 리소스에 대한 제한을 지정하여 보안 강화
    </br>

    ``` js
    //server.js
    app.use((req, res, next) => {
        res.setHeader("Access-Control-Allow-Origin", "*");
        res.header(
            "Access-Control-Allow-Headers",
            "Origin, X-Requested-With, Content-Type, Accept"
        );
        next();
    });
    ```