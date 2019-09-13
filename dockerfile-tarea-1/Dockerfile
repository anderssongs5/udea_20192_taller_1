FROM node:12.10.0-alpine

ENV APP_HOME /usr/src/app

EXPOSE 3000

RUN apk add --no-cache tini

WORKDIR $APP_HOME

COPY package.json .

RUN npm install \
    && npm cache clean --force

COPY . .

ENTRYPOINT ["sh", "-c"]
CMD ["/sbin/tini -- node ./bin/www"]
