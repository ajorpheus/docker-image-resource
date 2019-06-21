# stage: builder
FROM concourse/golang-builder AS builder

COPY . /go/src/github.com/concourse/docker-image-resource
ENV CGO_ENABLED 0
COPY assets/ /assets
RUN go build -o /assets/check github.com/concourse/docker-image-resource/cmd/check
RUN go build -o /assets/print-metadata github.com/concourse/docker-image-resource/cmd/print-metadata
RUN go build -o /assets/ecr-login github.com/concourse/docker-image-resource/vendor/github.com/awslabs/amazon-ecr-credential-helper/ecr-login/cmd
