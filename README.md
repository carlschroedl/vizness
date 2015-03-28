##Development##

###Install System Dependencies###
 - [git](http://git-scm.com/)
 - [nodejs](https://nodejs.org/)
 - bower and gulp : ```npm install bower gulp -g```

###Optionally###
 - If you want do syntax-checking on a JavaScript file on-demand, install jshint : ```node install -g jshint```. Subsequently you can check the syntax of a JavaScript file by running : ```jshint YOUR_FILENAME_HERE```

###Set up the App###
 - Fork and clone this repository.
 - Change to the directory where you cloned.
 - Now you will install system-level packages required by this project. These packages help automate our development tasks. For example: wiredep (More on that later). Run:
```
npm install
```
 - Now you will install web packages. These are javascript or css libraries that we build our application on top of. For example: bootstrap.
```
bower install
```
 - Now you will build the project. This performs automatic tasks like less->css compilation, javascript linting, and running tests.
```
gulp build
```

 - Now you will run the project in the browser. 
```
gulp serve
```
The command keeps running until you stop it with Ctl+C / Cmd+C. The command watches your source files for changes and refreshes the browser automatically.

####Adidng New Libraries####
Below we recommend a way to add JS or CSS browser dependencies to the project. We'd like contributors to give it an honest try, but we don't want it to be a barrier to contribution. If you find yourself getting unduly held up by the process, go ahead and check the JS/CSS library files into the repo just as you would in a project where the dependencies are managed ad-hoc - someone else can formalize your new dependencies after the pull request has been merged.

We are using bower to manage web packages. Find the library you want at the [Bower Package Registry](http://bower.io/search/). Once you have the name of the package, install it:
```
npm install YOUR_PACKAGE_NAME_HERE --save
```
The ```--save``` option is important because it will automatically update *bower.json*. Recording all of the project's bower dependencies in this file is important because it keeps everyone on the same page -- after people pull your updated bower.json they can simply run ```bower install``` to use the same dependencies as you.

Now that you have the library's files, you can automatically include a reference to them in index.html by running:
```
gulp wiredep
```

####Debugging LESS Files####
To debug LESS, follow the instructions on this site to enable CSS source maps in chrome:
http://robdodson.me/debug-less-with-chrome-developer-tools/#settingupchromeahrefidsettingupchromea
You only need to do the instructions under the 'Setting Up Chrome' section. The rest is already taken care of for you.
