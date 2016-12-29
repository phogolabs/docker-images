FROM ruby:2.3.3
MAINTAINER engineering@phogolabs.com

# UTF-8 SYSTEM LOCALE
# https://oncletom.io/2015/docker-encoding/
ENV LANG C.UTF-8
ENV DEBIAN_FRONTEND noninteractive

RUN apt-get -qq update
RUN apt-get -qq install  -y --no-install-recommends ca-certificates
RUN rm -rf /var/lib/apt/lists/*
RUN update-ca-certificates -v

RUN gem install bundler --no-ri --no-rdoc
RUN gem install nokogiri --no-ri --no-rdoc
RUN gem install rspec --no-ri --no-rdoc
RUN gem install capybara --no-ri --no-rdoc
RUN gem install webmock --no-ri --no-rdoc
RUN gem install rake --no-ri --no-rdoc
RUN gem install rack --no-ri --no-rdoc
RUN gem install sinatra --no-ri --no-rdoc
