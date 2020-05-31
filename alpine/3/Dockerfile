FROM alpine:3.12
LABEL maintainer="yago.riveiro@gmail.com"

ARG VERSION=1.12
ENV VERSION $VERSION
ARG URL=https://github.com/tianon/gosu/releases/download/${VERSION}/gosu-amd64
ENV URL ${URL}

RUN apk add --no-cache --virtual build-dependencies \
    curl==7.69.1-r0 && \
    curl -L --fail --silent --show-error ${URL} > /usr/local/bin/gosu && \
    chmod +x /usr/local/bin/gosu && \
    apk del build-dependencies && \
    rm -rf /var/cache/apk/*
