FROM golang:1.7.3
MAINTAINER engineering@phogolabs.com

# UTF-8 SYSTEM LOCALE
# https://oncletom.io/2015/docker-encoding/
ENV LANG C.UTF-8

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get -qq update
RUN apt-get -qq install bash jq

RUN go get github.com/progrium/basht
