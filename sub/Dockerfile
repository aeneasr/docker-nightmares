FROM golang:1.7

RUN go get github.com/Masterminds/glide

WORKDIR /go/src/github.com/arekkas/docker-nightmares/sub
ADD ./glide.yaml /go/src/github.com/arekkas/docker-nightmares/sub/glide.yaml
ADD ./glide.lock /go/src/github.com/arekkas/docker-nightmares/sub/glide.lock
RUN glide install

ADD . /go/src/github.com/arekkas/docker-nightmares/sub
RUN go install github.com/arekkas/docker-nightmares/sub

ENTRYPOINT sub foo

EXPOSE 4444