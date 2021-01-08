# BSD Education Docker Images

This repository contains custom docker images to use in continuous integration.

## Images

### build-deploy

Includes:
* node
* yarn
* aws-cli
* eb-cli

### testing

An extended postgres image that comes with pre-created databases for testing.

## How it works

Pushing commits and tags to BitBucket will result in a public bsdlaunchbox Docker image being built automatically by [Docker Hub](https://hub.docker.com/u/bsdsystems).

## Deploying new versions

Use git tags to define the versions of the Docker image:
`git tag -a build-deploy/v2 -m "install foobar"`

Preferably, add the tag before you push the commit, but if you have already pushed the commit then use `git push origin build-deploy/v2`.
