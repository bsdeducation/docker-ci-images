# BSD Education Docker Images

This repository contains custom docker images for use in continuous integration/deployment.

## Images

### build-deploy

Includes:
* node
* yarn
* aws-cli
* eb-cli
* tar

### testing

An extended postgres image that comes with pre-created databases for use when running unit tests.

## How it works

Pushing commits and tags to GitHub will result in a public [bsdeducation](https://hub.docker.com/u/bsdeducation) Docker image being built automatically by Docker Hub.

This git repo has various Dockerfiles in folders, and Docker Hub has multiple repositories each with different configuration to watch for tags on this git repo and to rebuild the appropriate Dockerfile to update the Docker image.

## Deploying new versions

Create a new tag:
* commit your changes
* `git tag -a build-deploy/v2 -m "install foobar"`
* `git push origin build-deploy/v2`

Moving an existing tag to a later commit:
* commit your changes
* ``git tag -a -f build-deploy/v1 `git rev-parse HEAD` ``
* `git push --force origin build-deploy/v1`

Either way, Docker Hub should automatically rebuild after the commit and tag are pushed to GitHub.