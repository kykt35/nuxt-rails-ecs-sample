FROM ruby:2.6.3-slim
ENV LANG C.UTF-8

RUN apt-get update -qq \
  && apt-get install -y build-essential default-libmysqlclient-dev \
  && rm -rf /var/lib/apt/lists/* \
  && gem update
RUN gem install bundler

WORKDIR /app
ADD Gemfile /app/
ADD Gemfile.lock /app/

ADD . /app
RUN bundle install -j4 --path vendor/bundle
