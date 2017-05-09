# Environment Setup (Mac only)

## Software installation

1. Download and install Docker by clicking [here](https://docs.docker.com/engine/installation/)


## Accounts setup

1. Get an account on https://hub.docker.com/ and ask to be added to the inkinisis group (to download private images)
1. Use your terminal to login to your docker hub account by issuing: ```docker login```
1. Create a new github account and ask to be added in the inkinisis team so that you get access to all inkinisis repos


## Repos and source code setup

Each developer is immediately cloning the origin repo instead of forking first. As a convention, each developer branch
is prefixed by their username (e.g smich_<branch_name>) and after is merged to the master branch, the developer has to
clean-up their branches.

1. Clone the inkinisis infrastructure repo into `~/inkinisis`
1. Clone the inkinisis app repo into `~/inkinisis/app/src`
1. symlink your 'inkinisis_src_folder' to `/private/inkinisis`


## Node and npm management

1. Install nvm using brew to easily control multiple node versions: `brew update && brew install nvm`
1. Install node *v6.9.2*: `nvm install v.6.9.2`
2. Set this node version as the default one: `nvm alias default 6.9.2`

## Local environment setup

1. Install required npm modules: `cd ~/inkinisis/inkinisis-app/src && npm install`
1. Build the containers - this will take some time as it needs to fetch container images from docker hub: `cd ~/inkinisis && docker-compose build`

# Everyday dev commands in Docker

check application logs:
```sh
docker exec -it inkinisis_app_1 bash -c "pm2 logs"
```
reload application server:
```sh
docker exec -it inkinisis_app_1 bash -c "pm2 reload ecosystem.config.js --only app-dev"
```
start a bash session to run any command in the container:
```sh
docker exec -it inkinisis_app_1 bash
```

# Test production build

- Compile assets in your host using webpack<sup>[1](#webpack-installation)</sup>: 
```sh 
NODE_ENV=production webpack -p
```

- Stop the dev environment: 
```sh
docker exec -it inkinisis_app_1 bash -c "pm2 stop ecosystem.config.js --only app-dev"
```

- Start the production environment: 
```sh
docker exec -it inkinisis_app_1 bash -c "pm2 start ecosystem.config.js --only ikapp"
```

### Footnotes

<sup><a name="webpack-installation">1</a></sup>Run the following to install webpack:
```sh
npm install -g webpack
```
