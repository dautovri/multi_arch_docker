## Multi-Arch docker image and manifest

Build and push 
```
# AMD64
$ docker build -t your-username/multiarch-example:manifest-amd64 --build-arg ARCH=amd64/ .
$ docker push your-username/multiarch-example:manifest-amd64

# ARM32V7
$ docker build -t your-username/multiarch-example:manifest-arm32v7 --build-arg ARCH=arm32v7/ .
$ docker push your-username/multiarch-example:manifest-arm32v7

# ARM64V8
$ docker build -t your-username/multiarch-example:manifest-arm64v8 --build-arg ARCH=arm64v8/ .
$ docker push your-username/multiarch-example:manifest-arm64v8
```

Manifest 

```
docker manifest create \
your-username/multiarch-example:manifest-latest \
--amend your-username/multiarch-example:manifest-amd64 \
--amend your-username/multiarch-example:manifest-arm32v7 \
--amend your-username/multiarch-example:manifest-arm64v8 

```


Result: 

https://hub.docker.com/repository/docker/dautovri/multiarch-example
