## Build a docker image to allow compiling golang scripts in this repo

```
cd $REPOSITORY_ROOT # cd into the repository root
docker build -t go-lang-builder -f dockerfiles/go-lang-builder/Dockerfile .
```

## Use the image to compile whichever golang script you wish

Example:

```
docker run -v $(pwd)/assets:/assets -v $(pwd):/go/src/github.com/concourse/docker-image-resource go-lang-builder  go build -o /assets/check /go/src/github.com/concourse/docker-image-resource/cmd/check
```
