FROM node:9.4.0-alpine

ARG VCS_REF
ARG BUILD_DATE
ARG IMAGE_TAG_REF

ENV GIT_SHA $VCS_REF
ENV IMAGE_BUILD $BUILD_DATE
ENV IMAGE_TAG $IMAGE_TAG_REF

WORKDIR /usr/srv/app
COPY package*.json ./
RUN npm install

COPY . .
RUN apk --no-cache add curl
EXPOSE 8080

CMD [ "npm", "run", "container" ]
