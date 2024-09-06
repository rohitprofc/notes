# Publish React Applications to Github Pages

## 1. Create a React Application:
- `npx create-react-app <app_name>` 

- `cd <app_name>`

- `npm start`

## 2. Install gh-pages using npm:

- `npm install gh-pages --save-dev`

> Make sure you have **`import React from 'react'`** at top of **src/App.js**

## 3. Modify Scripts:
### Package.json
```
{
    "homepage": "https://<profile-name>.github.io/<repo-name>",
},

 "scripts": {
    "start": "react-scripts --openssl-legacy-provider start",
    "build": "react-scripts --openssl-legacy-provider build",
    //...
    "predeploy": "npm run build",
    "deploy": "gh-pages -d build"
  },
  
```
## 4. Deploy Site at Github Pages
### Connecting local folder to cloud repository
- `git init`

- `git commit -am "commit-message"`

- `git remote add origin <repo-link>` <br><br>

### Deploying site

- `npm run deploy`

### Pushing to repository

- `git push`