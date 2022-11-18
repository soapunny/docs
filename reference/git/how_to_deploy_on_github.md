# __Production on github__
<br/></br>

## __Node.js__

1. Add remote to the current project.
2. Install 'gh-pages' package.
```
 $  npm i gh-pages
```
3. open package.json and write as below.
```json
    //when you call deploy, it will call predeploy first.
    "scripts": {
    ...
    "deploy": "gh-pages -d build",
    "predeploy": "npm run build"
    },
    "dependencies": {
    ...
    },//Register server
    "homepage": "https://[github-username].github.io/[project-name]"
```
4. deploy build file to the remote server.(It might take time)
```
 $  npm run deploy
```
5. Few minutes later, connect to the url you wrote.
```
    https://[github-username].github.io/[project-name]
```