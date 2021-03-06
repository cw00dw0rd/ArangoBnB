# ArangoBnB

This web app is being created to showcase the GeoJSON functionality of ArangoSearch and to provide an example of ArangoDB being used in a JavaScript stack.

To get started:
* Say hello in the [GitHub Discussions](https://github.com/cw00dw0rd/ArangoBnB/discussions)
* Check out the project todos:
  * [Primary Project board (Vue frontend & Backend tasks)](https://github.com/cw00dw0rd/ArangoBnB/projects/1)
  * [React Project board](https://github.com/users/cw00dw0rd/projects/1), (thanks [@couds](https://github.com/couds) and [@lostpebble](https://github.com/lostpebble) for leading the react version.)
* The dataset will need some modeling changes to take advantage of ArangoDB features so keep an eye out for changes to the dataset task [#16](https://github.com/cw00dw0rd/ArangoBnB/issues/16).
  * The dataset we are using can be found [here](https://drive.google.com/drive/folders/1crMM2RRpdVgi7gkblAlAZXTvIoNNVYbT?usp=sharing). We will make new folders for new dumps when necessary, always use the most recent dump.
* We now have a community projects Slack channel, [join us](https://arangodb-community.slack.com/archives/C01MLH491UM)!

Some goals for the project include:
* Search an AirBnB dataset to find rentals nearby a specified location
* Filter these based on keywords, date, and number of guests
* Natural language search (Ex: Houses in Florida with pools.)
* Index data using ArangoSearch Views
* Use AQL for all queries

We would enjoy having anyone from the community participate in the project development!
If you have any suggestions or features that you would like to be added start a discussion or open an issue.

# Contributing

## Project Setup

Currently, there are a couple ways to get started:
* [With Docker Compose](#with-docker-compose)
* [NPM and Self-Installed ArangoDB](#npm-and-self-install)
  * [Backend](#npm-backend-setup) 
  * [Vue](#npm-vue-setup) 
  * [React](#npm-react-setup) 

<h2 id="with-docker-compose">Using Docker Compose</h2>

- First you need to download the most up to date dump of the DB from [here](https://drive.google.com/drive/folders/1crMM2RRpdVgi7gkblAlAZXTvIoNNVYbT?usp=sharing)
- Extract the content inside the folder database/dumps. Its should looks like
```
dumps
|_ arangobnb.view.json
|_ arangobnb.view.json:Zone.Identifier
...
```

- Run `docker-compose up`. (The first time could take a few minutes, the docker images are beign build and the database dump its beign restored)

- Now you can access the Arango Web Interface in [http://localhost:8529](http://localhost:8529)
- Vue Frontend [http://localhost:8080](http://localhost:8080)
- React Frontend [http://localhost:8081](http://localhost:8081)
- Backend (API) [http://localhost:8001](http://localhost:8001)



<h2 id="npm-and-self-install">Using NPM and Self-Installed ArangoDB</h2>

### ArangoDB Installation

This project uses features from the upcoming 3.8 version of ArangoDB. To get started you will need the nightly build version of ArangoDB.
For more information on how to get a nightly build please see the [nighly builds page](https://www.arangodb.com/nightly-builds/).

Currently, the changes are in `3.8.0` so make sure to use the `3.8.0-nightly` build.
For example, if you are using docker:
```
docker pull arangodb/arangodb-preview:3.8.0-nightly

docker run -d -e ARANGO_ROOT_PASSWORD="test" -p 8529:8529 arangodb/arangodb-preview:3.8.0-nightly

```

<h2 id="npm-backend-setup">Backend</h2>

```
npm run install-backend

npm run serve-backend
```
You should receive the following message:
```
ArangoBnb API Backend listening on :5000
```
Note that either the `server_config.js` file or `.env` file in the backend folder must be updated with your ArangoDB depolyment information.

### Dependency Management 
Each frontend maintains its own package.json for dependencies.
The root package.json handles the installation of packages for whichever package you choose to install.
Running `npm install` will install both sets of packages for Vue and React.

If you would like to only install the individual packages append the framework name. ie: `npm run install-vue`

#### Environment Variables

This project uses `.env` and `.env.local` for the various environment variables needed, see the [Vue docs](https://cli.vuejs.org/guide/mode-and-env.html#modes) for more info. You will mostly need to pay attention to and update the variables in `.env.local`.

Since `.env.local` will not be included in PR's, this list should be updated when a PR adds to these variables.

Currently, these are the needed variables.

##### `.env`

`VUE_APP_API_ENDPOINT`

##### `.env.local`


<h2 id="npm-vue-setup" >Vue Project Setup</h2>

From the project root directory run:

```shell
npm install
# or
npm run install-vue
```

### Vue Compiles and hot-reloads for development

```shell
npm run serve
```

### Vue Compiles and minifies for production

```shell
npm run build
```

### Vue Lints and fixes files

```shell
npm run lint
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).

<h2 id="npm-react-setup">React Project Setup</h2>

From the project root directory run:

```shell
npm install
# or
npm run install-react
```

### Serve the react fronted

```shell
npm run serve-react
```
