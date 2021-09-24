FROM golang:1.15-alpine3.14 AS go
FROM alpine
LABEL maintainer="Rehtt. https://github.com/Rehtt/gocv-docker"
COPY --from=go /usr/local/go /usr/local/go
ENV PATH=$PATH:/usr/local/go/bin
ENV PKG="sudo \
        git \
        make \
        cmake \
        gcc \
        g++ \
        curl \
        pkgconfig \
        opencv-dev"
ENV GOPROXY=https://goproxy.io,direct
RUN apk --no-cache add ${PKG} && \
    go get -v gocv.io/x/gocv &&\
    go run /root/go/src/gocv.io/x/gocv/cmd/version/main.go && \
    rm -rf /var/cache/apk/*
