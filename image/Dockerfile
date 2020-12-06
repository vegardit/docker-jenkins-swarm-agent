# Copyright 2020 by Vegard IT GmbH, Germany, https://vegardit.com
# SPDX-License-Identifier: Apache-2.0
#
# Author: Sebastian Thomschke, Vegard IT GmbH
#
# https://github.com/vegardit/docker-jenkins-swarm-agent
#

# https://github.com/alpinelinux/docker-alpine/blob/master/Dockerfile
FROM alpine:3

LABEL maintainer="Vegard IT GmbH (vegardit.com)"

ARG BASE_LAYER_CACHE_KEY

ARG JRE_PACKAGE=openjdk8-jre-base

RUN \
  set -eu && \
  echo "#################################################" && \
  echo "Installing OS updates..." && \
  echo "#################################################" && \
  apk update && \
  apk upgrade && \
  #
  echo "#################################################" && \
  echo "Installing required packages..." && \
  echo "#################################################" && \
  apk add curl docker-cli git $JRE_PACKAGE && \
  #
  echo "#################################################" && \
  echo "Removing logs, caches and temp files..." && \
  echo "#################################################" && \
  rm -rf \
     /tmp/* \
     /var/cache/apk/* \
     /var/tmp/*

ARG BUILD_DATE
ARG GIT_COMMIT_HASH
ARG GIT_REPO_URL

LABEL \
  org.label-schema.schema-version="1.0" \
  org.label-schema.build-date=$BUILD_DATE \
  org.label-schema.vcs-ref=$GIT_COMMIT_HASH \
  org.label-schema.vcs-url=$GIT_REPO_URL
