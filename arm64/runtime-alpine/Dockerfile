FROM golang:1.15-alpine3.14
LABEL maintainer="Rehtt. https://github.com/Rehtt/gocv-docker"
ENV PKG="git \
        gcc \
        g++ \
        pkgconfig \
        opencv-dev"
ENV GOPROXY=https://goproxy.io,direct
RUN apk --no-cache add ${PKG} && \
    go get -v gocv.io/x/gocv &&\
    rm -rf /var/cache/apk/*
