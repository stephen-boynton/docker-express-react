# Full Stack React Docker Build

This uses `express generator` for the backend and `create-react-app` for the frontend. This is based in part on [Calweb's Api-Driven-Demo](https://github.com/calweb/api-driven-demo) and [Jesse Kinkead's Dockerizing a React Application](https://medium.com/ai2-blog/dockerizing-a-react-application-3563688a2378).

For the most part you can copy and paste this repository and edit to your hearts content. There are a few step's you'll need to take immediately following the `create-react-app` initiation. This come's from Mr. Kinkead's Medium post.

`cd` into the React application directory and run `npm run eject`. You will be prompted with "This is permanent, are you sure?" Say yes.

Then go to the package.json file in the React app and add the following code:

``` json
"optionalDependencies": {
  "fsevents": "*"
},
```

You will then need to run the following scripts in the command line in order:

``` s
$ npm prune
$ npm dedupe
$ npm install
$ npm shrinkwrap --dev
```

You can then go to your root directory and run:

```s
$ docker-compose build
$ docker-compose up
```
