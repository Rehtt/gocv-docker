FROM golang:1.17.1-alpine3.14
LABEL maintainer="Rehtt. https://github.com"
ENV PKG="git \
        gcc \
        g++ \
        pkgconfig \
        opencv-dev"
ENV GOPROXY=https://goproxy.io,direct
RUN apk --no-cache add ${PKG} && \
    rm -rf /var/cache/apk/*
