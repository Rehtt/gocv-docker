FROM golang:1.15-stretch
LABEL maintainer="Rehtt. https://github.com/Rehtt/gocv-docker"
ENV PKG="sudo \
         cmake"
WORKDIR /
RUN apt update && apt upgrade -y && apt install -y ${PKG} && \
    git clone https://github.com/hybridgroup/gocv.git && cd gocv && \
    make install_static ;exit 0 && \
    sed -i "/#cgo LDFLAGS/c\#cgo LDFLAGS: $(pkg-config --libs --static opencv4)" cgo_static.go && \
    apt purge ${PKG} && apt autoremove && \
    apt autoclean 
ENV CGO_LDFLAGS="-extldflags '-static'"