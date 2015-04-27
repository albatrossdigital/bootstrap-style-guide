## Installation

#### Install node and dependencies

See INSTALL.md for node install directions!

#### Basic (repo and  already setup)
Just clone the repo, npm install and run grunt:
```
git clone git@github.com:albatrossdigital/<repoName>.git
cd pls
npm install && bower install 
grunt
```

#### Advanced (setting up a repo for the first time)
Create repo in github
* Click + up in the top-right
* Change account owner for repo to Albatross Digital
* Create a <repoName> for your styleguide (`goredmond-styleguide`). 
* Leave privacy on repo Public
```
git clone git@github.com:albatrossdigital/bootstrap-style-guide.git
mv bootstrap-style-guide <repoName>
cd <repoName>
git remote set-url origin git@github.com:albatrossdigital/<repoName>.git
git push origin gh-pages
npm install && bower install 
grunt
```

## Using

### Git

#### Pushing changes
```
git status
git commit -m "msg" filenames
git push origin master
```

#### Push changes to gh-pages branch
```
grunt github
```

### Typekit urls
```
albatrossdigital.github.io,127.0.0.1:9000,*.albatrossdemos.com
```

### Sass

#### Important files

**app/scss/app.scss**
Imports all the global code into one file. If you create any new partials, they will have to be included in this file

**app/scss/_local-variables.scss**
Sets up reusable variables, and bootstrap variables for the sass code base

**app/scss/_mixins.scss**
Reusable code with varying degrees of complexity.

**app/scss/_styleguide-only.scss**
Code only meant to help layout the styleguide, not to be used for production down the line

**app/scss/components/{files}**
Any modular code meant for production.  Best practice is to create a new partial for any distinct css module.  Easiest way is to just copy boostrap's convention: bootstrap-style-guide/app/bower_components/bootstrap-sass-official/assets/stylesheets/bootstrap 

**app/scss/_appstyles.scss**
Any general code that doesn't fit into app/scss/components/* or other partials.  This file should be as small as possible, as anything here will need to still be ported to production and no one wants a "garbage" file.

#### Using the responsive mixin "respond"

```scss
// Mobile
@include respond($xs-only) {
  // Code in here
}

// Tablet + mobile
@include respond($sm-and-down) {
  // Code in here
}

// Tablet up
@include respond($sm-up) {
  // Code in here
}

// Tablet only
@include respond($sm-only) {
  // Code in here
}

// Laptop + tablet + mobile
@include respond($md-and-down) {
  // Code in here
}

// Laptop only
@include respond($md-only) {
  // Code in here
}

// Laptop up
@include respond($md-up) {
  // Code in here
}

// Large screen
@include respond($lg-up) {
  // Code in here
}
```

#### Installing custom fonts
Add this to a sass file. You can use https://fontie.flowyapps.com/home or http://www.flaticon.com/font-face to create all of the varients if necessary.
```
@font-face
  font-family: '<fontname>'
  src: url('../fonts/<fontname>.eot')
  src: url('../fonts/<fontname>.eot?#iefix') format('embedded-opentype'), url('../fonts/<fontname>.woff') format('woff'), url('../fonts/<fontname>.ttf') format('truetype'), url('../fonts/<fontname>.svg') format('svg')
  font-weight: normal
  font-style: normal
```
