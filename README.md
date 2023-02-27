# BSD Education Docker Images

This repository contains custom docker images for use in continuous integration/deployment.

## Images

### build-deploy

Includes:
* node
* yarn
* aws-cli
* eb-cli

### postgres

An extended postgres image that comes with pre-created databases for use when running unit tests.


## Deploying new versions

After writing your image you can build it with specifying a tag name and use the following command

`docker build -t bsdeducation/ci-build-deploy:v3 .`

And then after you build your image you can now set your credentials to upload to docker hub using

`docker login`

And finally push your image into docker hub using

`docker push bsdeducation/ci-build-deploy:v3`

At the end you should find your version on docker hub here

`https://hub.docker.com/repository/docker/bsdeducation/ci-build-deploy/general`
