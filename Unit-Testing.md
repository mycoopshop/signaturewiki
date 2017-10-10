Installing Jasmine standalone

Download the latest Jasmine release from the [Jasmine release page][1]: 

Running Jasmine locally

1. Run Jasmine in the browser by downloading the zip file, extracting it, the referencing the files as follows:

    <link rel="shortcut icon" type="image/png" href="jasmine/lib/jasmine-2.0.0/jasmine_favicon.png">
    `<link rel="stylesheet" type="text/css" href="jasmine/lib/jasmine-2.0.0/jasmine.css">`

    `<script type="text/javascript" src="jasmine/lib/jasmine-2.0.0/jasmine.js"></script>`
    `<script type="text/javascript" src="jasmine/lib/jasmine-2.0.0/jasmine-html.js"></script>`
    `<script type="text/javascript" src="jasmine/lib/jasmine-2.0.0/boot.js"></script>`
     
Installing Jasmine using npm ([Node Package Manager][2])

1. Set up project directory for Jasmine
 
      Create a folder and run `npm init` this will create an empty `package.json` file and will ask some questions about your project to fill project `json` file.

   Add 2 directories `app` - for the Server and `spec` - for tests 

2. Get Jasmine

    From root project directory run  

    `npm install jasmine-node --save` 

    `npm install request --save`

    `npm install express --save`

    this will get you the packages 

    `./node_packages/.bin/jasmine-node spec` will run jasmine binary

    After this your `package.json` should look similar to this

   package.json file, after which that file should look like this:

  

      {
          "name": "Jasmine",
          "version": "0.0.1",
          "description": "Jasmine",
          "main": "index.js",
          "scripts": {
            "test": "./node_modules/.bin/jasmine-node spec"
          },
          "author": "Me",
          "license": "ISC"
        }



Install with npm

    npm install -g jasmine

If being used with karma, install `karma-jasmine`
    
    npm install --save-dev karma-jasmine


  [1]: https://github.com/jasmine/jasmine/releases

  [2]: https://www.npmjs.com/