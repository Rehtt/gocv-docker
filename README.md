# 构建
```shell
docker build -t gocv .
```

# 静态编译
```shell
docker run \
    --rm    \
    -v /root/test:/build \
    gocv \
    bash -c `go build -tags static --ldflags '-extldflags "-static"' -o static_version /build/main.go`
```