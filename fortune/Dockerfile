ARG VER=18.2.0
FROM node:${VER}
LABEL developer=edmundc

WORKDIR /app

# curl is already installed

# add files
ADD package.json .
ADD package-lock.json .
ADD views views
ADD public public
ADD main.js .

# install
RUN npm ci

#run the app
ENV APP_PORT=3000
EXPOSE $APP_PORT
HEALTHCHECK --interval=30s --timeout=5s --start-period=5s --retries=3 \
  CMD curl -s http://localhost:${APP_PORT}/healthz  || exit 1

ENTRYPOINT [ "node", "main.js" ]
