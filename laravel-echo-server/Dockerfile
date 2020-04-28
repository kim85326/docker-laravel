ARG VERSION="10.15.3"

FROM node:${VERSION}

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

COPY ./package.json /usr/src/app/
COPY ./laravel-echo-server.json /usr/src/app/
RUN npm install

CMD ["npm", "start", "--", "--force"]
