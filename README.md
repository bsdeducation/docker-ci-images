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

This repo currently has 2 Dockerfiles and Docker Hub has 2 repositories with different configuration to observe tags on git and use the appropriate Dockerfile to rebuild the image.

## Deploying new versions

Use git tags to define the versions of the Docker image:
`git tag -a build-deploy/v2 -m "install foobar"`

Preferably, add the tag before you push the commit, but if you have already pushed the commit then use `git push origin build-deploy/v2`.

Moving an existing tag to a later commit:
* commit your changes
* get the latest commit ID: `git rev-parse HEAD`
* `git tag -a -f build-deploy/v1 <latest commit ID>`