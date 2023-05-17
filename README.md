# How to start the app in dev

`npm run devstart`

## populate your local mongodb

`node populatedb "mongodb://localhost:27017/local_library?retryWrites=true&w=majority"`

## steps to deploy on railway

1. copy the version from `node -v` and paste in in package.json under `engines.node`.
2. in app.js replace `const mongodb = '..'` with `const mongoDB = process.env.MONGODB_URI || 'mongodb://localhost:27017/local_library'`
