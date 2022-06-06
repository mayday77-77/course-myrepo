ARG VER=3.11.0b3-alpine3.16
FROM python:${VER}
LABEL developer=edmundc

WORKDIR /app

# curl is already installed

# add files
ADD public public
ADD templates templates
ADD utils.py .
ADD main.py .
ADD requirements.txt .
ADD run.sh .

# install
RUN pip3 install -r requirements.txt

#run the app
ENV PORT=3000
EXPOSE $PORT
#HEALTHCHECK --interval=30s --timeout=5s --start-period=5s --retries=3 \
#  CMD curl -s http://localhost:${APP_PORT}/healthz  || exit 1

ENTRYPOINT ["/app/run.sh", "&"]

