# apollo-server-gcp-sls

Apollo GraphQL server with Express On Google Cloud Platform (GCP) Function (not Firebase Function) using Serverless for deployment

Related Article: https://codeburst.io/apollo-graphql-server-express-google-cloud-function-serverless-framework-dbb6b5cf4bb3

## Important - Babel

You will need Babel to transpile your ES6 code to ES5 in order for the application to work


Create .babelrc file with the following contents, the node version follows the one on GCP.

```
{
  "presets": [
    ["@babel/env", {
      "targets": {
        "node": "6.11.5"
      }
    }]
  ]
}
```

Add the following command to package.json, to transpile:

```
"es5": "babel src --out-dir dist --copy-files"
```

## Packages to install

### Dependencies

> Babel

```
babel-polyfill
babel-runtime
```

> Apollo & GraphQL

```
npm i -S apollo-server-express graphql graphql-tools
```

> you need the firebase packages to hook express to cloud functions

```
npm i -S body-parser express firebase-admin firebase-functions serverless-google-cloudfunctions
```

### DevDependencies

> Babel

```
npm i -D @babel/cli @babel/core @babel/preset-env babel-preset-es2015
```

## Reference

https://serverless.com/framework/docs/providers/google/guide/quick-start/

https://codeburst.io/graphql-server-on-cloud-functions-for-firebase-ae97441399c0

Note: If there is a serious deployment error and even a simple test application cannot deploy, goto Google Cloud Platform console, Deployment Manager, select the deployment to delete, then delete it!

## Configure

Configure your keyfile.sample.json file and save as keyfile.json

Configfure your serverless.sample.yml and save as serverless.yml

## Install & Deploy
```
npm i
npm run es5
serverless deploy
```

### Git

```
git init
git add README.md
git commit -m "first commit
git remote add origin git@github.com:ais-one/apollo-server-gcp-sls.git
# git remote add origin https://github.com/ais-one/apollo-server-gcp-sls.git
git push -u origin master
```

subscriptions-transport-ws graphql-subscriptions faker lodash
