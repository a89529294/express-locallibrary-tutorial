# How to start the app in dev

`npm run devstart`

## populate your local mongodb

`node populatedb "mongodb://localhost:27017/local_library?retryWrites=true&w=majority"`

## steps to deploy on railway

1. copy the version from `node -v` and paste in in package.json under `engines.node`.
2. in app.js replace `const mongodb = '..'` with `const mongoDB = process.env.MONGODB_URI || 'mongodb://localhost:27017/local_library'`
3. log in to railway with Github and create new project. Choose deploy from github repo.
4. After deployment, Go to settings and press Generate Domain button.
5. Go to project dashboard, click on + New button and choose database mongodb.
6. Copy mongodb connection string.
7. go to variables and add `MONGODB_URI` with value you just copied.
8. add `NODE_ENV` with value `production` as another variable.
