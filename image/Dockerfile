#syntax=docker/dockerfile:1.2
# Copyright 2020-2021 by Vegard IT GmbH, Germany, https://vegardit.com
# SPDX-License-Identifier: Apache-2.0
#
# Author: Sebastian Thomschke, Vegard IT GmbH
#
# https://github.com/vegardit/docker-jenkins-swarm-agent
#

# https://github.com/alpinelinux/docker-alpine/blob/master/Dockerfile
FROM alpine:3

LABEL maintainer="Vegard IT GmbH (vegardit.com)"

USER root

ARG BASE_LAYER_CACHE_KEY

ARG JRE_PACKAGE=openjdk8-jre-base

RUN --mount=type=bind,source=.shared,target=/mnt/shared \
  set -eu && \
  /mnt/shared/cmd/alpine-install-os-updates.sh && \
  #
  echo "#################################################" && \
  echo "Installing required packages..." && \
  echo "#################################################" && \
  apk --no-cache add curl docker-cli git $JRE_PACKAGE && \
  #
  /mnt/shared/cmd/alpine-cleanup.sh

ARG BUILD_DATE
ARG GIT_COMMIT_HASH
ARG GIT_REPO_URL

LABEL \
 org.label-schema.schema-version="1.0" \
 org.label-schema.build-date=$BUILD_DATE \
 org.label-schema.vcs-ref=$GIT_COMMIT_HASH \
 org.label-schema.vcs-url=$GIT_REPO_URL
