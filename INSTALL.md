
## Installing dependencies

### Install node

#### Windows --------------------------------


1. Read http://blog.teamtreehouse.com/install-node-js-npm-windows

2. Download installer and install https://nodejs.org/download/


#### Linux ----------------------------------


1. https://github.com/joyent/node/wiki/Installing-Node.js-via-package-manager

2. Follow directions


#### Macintosh -------------------------------


1. Get homebrew.  Probably already have this, if you don't run this from command line:

```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)" 
```

2. Get Node installed.  Just run this from command line

```
brew install node  
```

## Once Node is installed


#### 1. Get grunt installed globally.  From command line

```
npm install -g grunt-cli
# might need sudo
```

This might have some difficulty with permissions... either you can use "sudo" or look into making sure npm global installs are possible without it: http://stackoverflow.com/questions/16724259/npm-command-sudo-or-not

#### 2. Install bower globally

```
npm install -g bower
# might need sudo
```

This might have some difficulty with permissions... either you can use "sudo" or look into making sure npm global installs are possible without it: http://stackoverflow.com/questions/16724259/npm-command-sudo-or-not
  
#### 3. Install dependencies in the theme sub folder:

```
cd {where ever you put this}
npm install && bower install 
```

#### 4. Make sure grunt task runs... in same theme folder:

```
grunt
``` 