# alpine-node
Minimal [Node.js](https://nodejs.org/) [Docker](https://www.docker.com/) images built on [Alpine Linux](https://alpinelinux.org/)

## Versions
* latest, 6.2.0 – 46 MB (npm 3.x)
* lts, 4.4.4 – 36.31 MB (npm 2.x)

## Example
    # FROM 2toad/alpine-node:6.2.0
    FROM 2toad/alpine-node:4.4.4

    WORKDIR /src
    ADD . .

	RUN npm install

    EXPOSE 3000
    CMD ["node", "index.js"]

## Caveats

Alpine Linux uses musl, so you may run into some issues with environments expecting glibc (e.g., Kubernetes)

* http://gliderlabs.viewdocs.io/docker-alpine/caveats/
* https://github.com/gliderlabs/docker-alpine/issues/8

> Inspired by: https://github.com/mhart/alpine-node
