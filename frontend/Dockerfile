FROM node:11.1

WORKDIR /app

ENV PATH /app/node_modules/.bin:$PATH

RUN apt-get update && \
    apt-get install -y vim less

ENV TZ Asia/Tokyo
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

ADD package.json /app/package.json
ADD yarn.lock /app/yarn.lock
ADD . /app

RUN yarn install --no-progress --registry http://registry.npmjs.org/
ENV HOST 0.0.0.0
