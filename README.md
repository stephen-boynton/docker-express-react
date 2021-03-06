# Full Stack React Docker Build

This uses `express generator` for the backend and `create-react-app` for the frontend. This is based in part on [Calweb's Api-Driven-Demo](https://github.com/calweb/api-driven-demo) and [Jesse Kinkead's Dockerizing a React Application](https://medium.com/ai2-blog/dockerizing-a-react-application-3563688a2378).

Theoretically, you should be able to clone this repository and edit it to your own standards and then just use:

```s
$ docker-compose build
$ docker-compose up
```

And it should boot right up. If not, you can use the following process.

## Follow this to rebuild

For the most part you can copy and paste all of the Docker files in this repository, and edit to your hearts content. Inside the backend folder use the `express-generator` to create an express app called "app". Then in the frontend do the same thing but with `create-react-app`, also called "app". 

There are a few step's you'll need to take immediately following the `create-react-app` initiation. This come's from Mr. Kinkead's Medium post.

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
