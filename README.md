Development

Install
git
nodejs
gulp
bower

Optionally:
jshint

Fork and clone this repository.
Change to the directory where you cloned.
Run:
$ npm install
This will install system-level packages. These packages help automate our development tasks. For example: wiredep (More on that later).

$ bower install
This will install web packages. These are javascript or css libraries that we build our application on top of. For example: bootstrap.

$ gulp build
This will perform automatic tasks like less->css compilation, javascript linting, and running tests.

$ gulp serve
If all goes well, a browser window will open showing the project. The command keeps running until you stop it with Ctl+C / Cmd+C. The command watches your source files for changes and refreshes the browser automatically.


Adidng new libraries:
We are using bower to manage web packages. Try to find the library you want here:
http://bower.io/search/
Install the package:
$ npm install YOUR_PACKAGE_NAME_HERE --save
The --save is important because it will update bower.json. Recording all of the project's bower dependencies in this file is important because it allows others to retrieve the correct dependencies by simply typing `bower install`.

Now that you have the library's files, include a reference to them by running:
$ gulp wiredep
This command will insert the library's CSS and javascript files into index.html for you.

Before you make further changes to the project, I suggest you commit the changes with a message like "Added bootstrap".


