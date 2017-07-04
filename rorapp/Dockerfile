#
#See https://docs.docker.com/compose/rails/#build-the-project
FROM ruby:2.3.4

RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs

RUN mkdir /rorapp

WORKDIR /rorapp

ADD Gemfile /rorapp/Gemfile

ADD Gemfile.lock /rorapp/Gemfile.lock

RUN bundle install

ADD . /rorapp
