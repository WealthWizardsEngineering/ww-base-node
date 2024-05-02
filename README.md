# ww-base-node

Reference image to use for building ww node services. Dockerfiles should reference FROM this image.

`FROM quay.io/wealthwizards/ww-base-node:alpine-20`

If alpine is not a suitable upstream image and a more complete image is required, please use the alternative:

`FROM quay.io/wealthwizards/ww-base-node:debian-20`

## Available versions

There are alpine and debian versions built.

The specific versions build are defined in the .versions file.

These are also tagged as major an minor versions, you should use the major version unless you have a good reason to be
more specific. This is so that images will be updated automatically.

For example:

Version defined in .versions file as '20.12.2' will produce the following tags:

* `quay.io/wealthwizards/ww-base-node:alpine-20`
* `quay.io/wealthwizards/ww-base-node:alpine-20.12`
* `quay.io/wealthwizards/ww-base-node:alpine-20.12.2`

* `quay.io/wealthwizards/ww-base-node:debian-20`
* `quay.io/wealthwizards/ww-base-node:debian-20.12`
* `quay.io/wealthwizards/ww-base-node:debian-20.12.2`

The last version defined in the .versions file will be tagged as alpine-latest and debian-latest.

## Updating

Update or add to the .versions file, there should be a single entry for each major and minor version.

## Builds

Builds are performed on circleci, all branches are built, but only master commits are pushed to quay.io.

## License

This repository and image are directly based off the official node image: https://hub.docker.com/r/library/node/

The source is available on Github: https://github.com/nodejs/docker-node

[License information](https://github.com/nodejs/node/blob/master/LICENSE) for the software contained in this image.
[License information](https://github.com/nodejs/docker-node/blob/master/LICENSE) for the Node.js Docker project.
