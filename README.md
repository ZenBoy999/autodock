 autodock

[![Build Status](https://travis-ci.org/prologic/autodock.svg)](https://travis-ci.org/prologic/autodock)
[![CodeCov](https://codecov.io/gh/prologic/autodock/branch/master/graph/badge.svg)](https://codecov.io/gh/prologic/autodock)
[![Go Report Card](https://goreportcard.com/badge/github.com/prologic/autodock)](https://goreportcard.com/report/github.com/prologic/autodock)
[![GoDoc](https://godoc.org/github.com/prologic/autodock?status.svg)](https://godoc.org/github.com/prologic/autodock)
[![](https://images.microbadger.com/badges/image/prologic/autodock.svg)](https://microbadger.com/images/prologic/autodock "Get your own image badge on microbadger.com")

[autodock](https://github.com/prologic/autodock) is a Daemon for
Docker Automation which enables you to maintain and automate your Docker
infrastructure by reacting to Docker or Docker Swarm events.

## Supported plugins:

autodock comes with a number of plugins where each piece of functionality is
provided by a separate plugin. Each plugin that is "connected" to autodock
will receive events (*such as Docker or Docker Swarm*) and perform appropriate
actions using a proxy to the Docker API.

autodock is also capable of receiving events from other external sources such
as [Docker Hub](https://hub.docker.com) or [Github](https://github.com)
webhooks to support things like CI/CD.

The following list is a list of the currently available plugins:

- [autodock-cron](https://github.com/prologic/autodock)
  Provides a *Cron* like scheduler for Containers/Services
- [autodock-logger](https://github.com/prologic/autodock-logger)
  Logs Dockers Events (*Reference Implementation*)

## Installation

### Docker

```#!bash
$ docker pull prologic/autodock
```

### Source

```#!bash
$ go install github.com/prologic/autodock
```

## Usage

### Docker

```#!bash
$ docker run -d -p 8000:8000 -v /var/run/docker.sock:/var/run/docker.sock prologic/autodock
```

For a full production-ready Docker Compose (*Stackfile*) see [here](./docker-compose.yml)

### Source

```#!bash
$ autodock
```

## License

MIT
