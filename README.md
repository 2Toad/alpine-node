# alpine-node

[![GitHub](https://img.shields.io/badge/GitHub-OpenSource-green.svg)](https://github.com/2Toad/alpine-node)
[![Docker](https://img.shields.io/badge/Docker-Hub-blue.svg)](https://hub.docker.com/r/2toad/alpine-node/)

Minimal [Node.js](https://nodejs.org/) [Docker](https://www.docker.com/) images built on [Alpine Linux](https://alpinelinux.org/)

## Versions

| Tags              | Node   | NPM     | Alpine | Image    |
|-------------------|--------|---------|--------|----------|
| `latest`, `7.4.0` | 7.4.0  | 4.0.5   | 3.5.0  | 53.50 MB |
| `6.3.0`           | 6.3.0  | 3.10.3  | 3.4.0  | 47.56 MB |
| `6.2.0`           | 6.2.0  | 3.9.2   | 3.3.0  | 46.00 MB |
| `lts`, `6.11.4`   | 6.11.4 | 3.10.10 | 3.6.0  | 49.40 MB |
| `6.9.4`           | 6.9.4  | 3.10.10 | 3.5.0  | 48.34 MB |
| `4.4.7`           | 4.4.7  | 2.15.8  | 3.4.0  | 36.33 MB |
| `4.4.4`           | 4.4.4  | 2.15.5  | 3.3.0  | 36.31 MB |

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
