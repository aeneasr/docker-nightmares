FROM golang:1.7

RUN go get github.com/Masterminds/glide

WORKDIR /go/src/github.com/arekkas/docker-nightmares/pub
ADD ./glide.yaml /go/src/github.com/arekkas/docker-nightmares/pub/glide.yaml
ADD ./glide.lock /go/src/github.com/arekkas/docker-nightmares/pub/glide.lock
RUN glide install

ADD . /go/src/github.com/arekkas/docker-nightmares/pub
RUN go install github.com/arekkas/docker-nightmares/pub

ENTRYPOINT pub foo

EXPOSE 4444