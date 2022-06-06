ARG VER=18.2.0
FROM node:${VER}
LABEL developer=edmundc

WORKDIR /app

# add files
ADD package.json .
ADD main.js .
ADD package-lock.json .
ADD views views
ADD public public

# install
RUN npm ci

#run the app
ENV APP_PORT=3000
EXPOSE $APP_PORT
ENTRYPOINT [ "node", "main.js" ]
