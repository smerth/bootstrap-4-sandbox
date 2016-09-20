# Bootstrap4 Sandbox 

> Built on Yeoman generator-bootstrap4 with the following additions:
>
> 1. grunt-gh-pages to push the dist folder to github pages
> 2. modified grunt tasks to process additional html pages
> 3. addition of panini for a fast and simple templating option

## Yeoman Generator

This Bootstrap 4 Sandbox is based on a Yeoman generator: [Generator Bootstrap4 by bassjobsen](https://github.com/bassjobsen/generator-bootstrap4/)

During the installation for this generator you can choose several configurations.  This sandbox does not use flex, but you can choose that if you want at the time of the install.  Or, modify Bootstrap 4 variables afterwards.

## Install from the generator

### Install the generator

```bash
Install: npm install -g generator-bootstrap4
```

### Run the generator

```bash
yo bootstrap4
```

### Choose options

Choose font-awesome and Octicons - because they are both great icon libraries...

Enable flexbox



## Install from this repo

```bash
git clone https://github.com/smerth/bootstrap-4-sandbox.git
```

Install bower deps

```bash
bower install
```

install npm deps

```bash
npm install
```

@ test folder <- check this...

```bash
bower install
```



### Build the App

```bash
grunt
```

This builds the app from the app folder and runs the Mocha test suite.

Leave this terminal window open to keep tests running in the background.

**Testing Note**: a project checked into source control and later checked out needs to have ```bower install``` run from the test folder as well as from the project root.

### Serve the dev environment

```bash
grunt serve
```

Serves the files from: .tmp
Serves files from: app
Watches files...

So in development you are editing the app folder and changes are updated automatically in the browser.

### Serve the dist folder

```bash
grunt serve:dist
```

Serves files from: dist (after building it...)

### Editing, Building and Watching

@ app/index.html

update the site title

```html
<h3 class="text-muted">Bootstrap 4 Sandbox</h3>
```

The dev server updates the content change automatically.

The dist folder needs to be rebuilt before the changes can be seen.

Stop the server ctl-c. and restart...

```bash
grunt serve:dist
```

Remember if you are pushing the dist folder to github pages using ```grunt-gh-pages``` you need to rebuild the dist folder before pushing to github.



## Pushing to Github Pages

Push using (grunt-gh-pages)[https://www.npmjs.com/package/grunt-gh-pages]

### grunt-gh-pages

install the plugin

```bash
npm install grunt-gh-pages --save-dev
```

enable (require) the plugin

@ Gruntfile.js

```json
module.exports = function (grunt) {

  // load module
  require('grunt-gh-pages')(grunt);
  
  ...
```



Add task to deploy the dist folder to gh-pages

@ Gruntfile.js

```json
  // Define the configuration for all the tasks
  grunt.initConfig({

    // Project settings
    config: config,

    // Push the dist folder to gh-pages
    'gh-pages': {
      options: {
        base: 'dist'
      },
      src: ['**']
    },
    
    ...
```



### Setup Git

Edit .gitignor

```yaml
# Apple stuff
.DS_Store
.tmp

# Caches
.sass-cache

# Modules
bower_components
node_modules

# Grunt generated builds
dist

```

Initialize git

```bash
git init
```

and 

```bash
git add .
```

and 

```bash
git commit -m "first commit"
```



### Push dist to gh-pages

```bash
 grunt gh-pages
```























Run the app in development mode

```bash
grunt serve
```







When developing serve the app folder which also runs grunt watch

To serve the app

grunt serve

To serve the dist folder

grunt serve:dist

To delploy to github pages

gulp deploy



Code in the app folder...

File structure





Install Bower dependancies

```bash
bower install
```



Grunt and Gulp

