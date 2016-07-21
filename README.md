# alpine-node

[![GitHub](https://img.shields.io/badge/GitHub-OpenSource-green.svg)](https://github.com/2Toad/alpine-node)
[![Docker](https://img.shields.io/badge/Docker-Hub-blue.svg)](https://hub.docker.com/r/2toad/alpine-node/)

Minimal [Node.js](https://nodejs.org/) [Docker](https://www.docker.com/) images built on [Alpine Linux](https://alpinelinux.org/)

## Versions

| Tags              | Node  | NPM    | Alpine | Image    |
|-------------------|-------|--------|--------|----------|
| `latest`, `6.2.0` | 6.2.0 | 3.9.2  | 3.3.0  | 46.0 MB  |
| `lts`, `4.4.4`    | 4.4.4 | 2.15.5 | 3.3.0  | 36.31 MB |

## Example
    FROM 2toad/alpine-node:latest
    # FROM 2toad/alpine-node:4.4.4

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
