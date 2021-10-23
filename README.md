# so the point is to create a statically linked musl rust binary

we are using docker with buildkit, so make sure to either
`export DOCKER_BUILDKIT=1`
or build with
`docker buildx build`

The Docker file is currently not that clean but we can fix that later.


### to run
```
docker build .
docker run -it IMAGE_ID
docker cp CONTAINER_ID:/app/target/x86_64-unknown-linux-musl/release/ps_rust
```

### improvements
1. haven't looked a whole lot into it but it might be better to use cargo-chef
   [saveing registry](https://newbedev.com/cache-rust-dependencies-with-docker-build)
2. maybe we can use Rusts docker images instead of downloading rust and installing (it takes a long time)



