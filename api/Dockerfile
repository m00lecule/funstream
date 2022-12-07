FROM golang:1.18-alpine AS builder

WORKDIR /go/src/github.com/m00lecule/funstream
COPY . /go/src/github.com/m00lecule/funstream
RUN go build -o app

FROM alpine:3.16
WORKDIR /api
COPY --from=builder /go/src/github.com/m00lecule/funstream .
EXPOSE 8080
ENTRYPOINT ["./app"]