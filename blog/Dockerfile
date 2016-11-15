FROM ubuntu:xenial
MAINTAINER Phogo Labs <engineering@phogolabs.com>

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get -qq update
RUN apt-get -qq install bash jq

ENV HUGO_VERSION 0.17
ENV HUGO_BINARY hugo_${HUGO_VERSION}-64bit.deb

ADD https://github.com/spf13/hugo/releases/download/v${HUGO_VERSION}/${HUGO_BINARY} /tmp/hugo.deb
RUN dpkg -i /tmp/hugo.deb	&& rm /tmp/hugo.deb
