# Cleanup-react-app

Cleanup your create-react-app. Removes commonly deleted files and boilerplate content from templates generated by create-react-app. Similar to cleanup-create-react-up, but more thorough.

## Instructions

It is reccomended that you install the package globally:

````shell
npm i -g cleanup-react-app
````

or

````shell
yarn global add cleanup-react-app
````

To use the package navigate to the directory to be cleaned up and run:

````shell
cleanup-react-app
````

## Intended use

It is intended that the package is run directly after running create-react-app.

````shell

create-react-app app-name

cd app-name

cleanup-react-app
````

## Operations

The package performs four operations.

### 1. Directory checks

First the contents of the directory to be cleaned are checked. This is to ensure the directory is an instance of create-react-app.

If missing or modified files are detected, a warning is thrown:

````shell
⚠️ Warning: Directory does not match create-react-app template.

Missing files:

<list of missing files>

Modified files:

<list of modified files>

Attempting to cleanup: /directory/being/cleaned
````

The user is then asked whether to proceed with the cleanup.

If this warning is thrown, pay attention to the printed directory. Attempting to clean a directory that is not a template instance of create-react-app may result in unintended files being overwritten/deleted.

The package checks the existence of:

>node_modules  
>public  
>public/favicon.ico  
>public/index.html  
>public/logo192.png  
>public/logo512.png  
>public/manifest.json  
>public/robots.txt  
>src  
>src/App.js  
>src/App.test.js  
>src/index.css  
>src/index.js  
>src/logo.svg  
>src/serviceWorker.js  
>src/setupTests.js  
>.gitignore  
>package.json  
>README.md  
>yarn.lock

and the content of:

>src/App.js  
>src/App.css  
>src/index.js  
>public/index.html  
>public/manifest.json  
>README.md  
>serviceWorker.js

### 2. Remove files

These files are removed:

> public/favicon.ico  
> public/logo192.png  
> public/logo512.png  
> src/logo.svg

### 3. Rename files

This file is renamed:

> App.js

to

> App.jsx

### 4. Rewrite files

These files are emptied of content:

> src/App.css  
> src/index.css  
> README.md

This file has most of its boilerplate removed:

> src/App.jsx

The new content is:

````jsx
import React from 'react';
import './App.css';
  
  function App() {
    return (
      <>
      </>
    );
  }

export default App;
````
