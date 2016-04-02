FROM golang

# Fetch dependencies
RUN go get github.com/tools/godep

# Add project directory to Docker image.
ADD . /go/src/github.com/excobox/excobox.github.io

ENV USER aididrizovic
ENV HTTP_ADDR :8888
ENV HTTP_DRAIN_INTERVAL 1s
ENV COOKIE_SECRET 23V8S0Wc-QAn9-vd

# Replace this with actual PostgreSQL DSN.
ENV DSN postgres://aididrizovic@localhost:5432/excobox.github.io?sslmode=disable

WORKDIR /go/src/github.com/excobox/excobox.github.io

RUN godep go build

EXPOSE 8888
CMD ./excobox.github.io