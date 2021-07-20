# vegardit/jenkins-swarm-agent

[![Build Status](https://github.com/vegardit/docker-jenkins-swarm-agent/workflows/Build/badge.svg "GitHub Actions")](https://github.com/vegardit/docker-jenkins-swarm-agent/actions?query=workflow%3ABuild)
[![License](https://img.shields.io/github/license/vegardit/docker-jenkins-swarm-agent.svg?label=license)](#license)
[![Docker Pulls](https://img.shields.io/docker/pulls/vegardit/jenkins-swarm-agent.svg)](https://hub.docker.com/r/vegardit/jenkins-swarm-agent)
[![Docker Stars](https://img.shields.io/docker/stars/vegardit/jenkins-swarm-agent.svg)](https://hub.docker.com/r/vegardit/jenkins-swarm-agent)
[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-v2.0%20adopted-ff69b4.svg)](CODE_OF_CONDUCT.md)

1. [What is it?](#what-is-it)
1. [License](#license)


## <a name="what-is-it"></a>What is it?

Lightweight Docker image based on [alpine:3](https://hub.docker.com/_/alpine?tab=tags&page=1&name=3) to be used in conjunction with the [Jenkins Docker Swarm](https://github.com/jenkinsci/docker-swarm-plugin) and [Docker Pipeline](https://plugins.jenkins.io/docker-workflow/) plugin to realize containerized builds within [Docker Swarm](https://docs.docker.com/engine/swarm/) clusters using a Docker-out-of-Docker (DooD) approach.

![](docs/cloud-config.png)

It is automatically built **daily** to include the latest OS security fixes.

The following packages are preinstalled:
1. [curl](https://pkgs.alpinelinux.org/package/edge/main/x86_64/curl)
1. [docker-cli](https://pkgs.alpinelinux.org/package/edge/community/x86_64/docker-cli)
1. [git](https://pkgs.alpinelinux.org/package/edge/main/x86_64/git)
1. [openjdk8-jre-base](https://pkgs.alpinelinux.org/package/edge/community/x86_64/openjdk8-jre-base) /
   [openjdk11-jre-headless](https://pkgs.alpinelinux.org/package/edge/community/x86_64/openjdk11-jre-headless)


## <a name="license"></a>License

All files in this repository are released under the [Apache License 2.0](LICENSE.txt).

Individual files contain the following tag instead of the full license text:
```
SPDX-License-Identifier: Apache-2.0
```

This enables machine processing of license information based on the SPDX License Identifiers that are available here: https://spdx.org/licenses/.
