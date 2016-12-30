FROM ruby:2.3.3
MAINTAINER Phogo Labs <engineering@phogolabs.com>

# UTF-8 SYSTEM LOCALE
# https://oncletom.io/2015/docker-encoding/
ENV LANG C.UTF-8

ENV DEBIAN_FRONTEND noninteractive

RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 93C4A3FD7BB9C367
RUN echo "deb http://ppa.launchpad.net/ansible/ansible/ubuntu trusty main" >> /etc/apt/sources.list
RUN apt-get -qq update
RUN apt-get -qq install  -y --no-install-recommends bash jq git ca-certificates curl ansible
RUN rm -rf /var/lib/apt/lists/*
RUN update-ca-certificates -v

# Install Hugo to generate new blog content
ENV HUGO_VERSION 0.17
ENV HUGO_BINARY hugo_${HUGO_VERSION}-64bit.deb

ADD https://github.com/spf13/hugo/releases/download/v${HUGO_VERSION}/${HUGO_BINARY} /tmp/hugo.deb
RUN dpkg -i /tmp/hugo.deb	&& rm /tmp/hugo.deb

#################
# Install Golang
#################
ENV GOLANG_VERSION 1.7.4

ADD https://storage.googleapis.com/golang/go${GOLANG_VERSION}.linux-amd64.tar.gz /tmp/golang.tar.gz
RUN tar -C /usr/local -xzf /tmp/golang.tar.gz && rm /tmp/golang.tar.gz

ENV GOPATH /go
ENV PATH $GOPATH/bin:/usr/local/go/bin:$PATH
RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 777 "$GOPATH"

RUN go get github.com/progrium/basht

###################
# Install Ruby
###################

RUN gem install bundler --no-ri --no-rdoc
RUN gem install nokogiri --no-ri --no-rdoc
RUN gem install rspec --no-ri --no-rdoc
RUN gem install capybara --no-ri --no-rdoc
RUN gem install webmock --no-ri --no-rdoc
RUN gem install rake --no-ri --no-rdoc
RUN gem install rack --no-ri --no-rdoc
RUN gem install sinatra --no-ri --no-rdoc
