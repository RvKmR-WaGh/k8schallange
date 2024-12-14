FROM golang:latest AS builder
WORKDIR /src
COPY test.go /src/test.go
RUN go mod init hello
RUN go build -o /bin/hello ./test.go


FROM builder AS pre-prod
COPY --from=builder /bin/hello /bin/hello
CMD ["/bin/hello"]

FROM builder as prod
COPY --from=builder /bin/hello /bin/hello
CMD ["/bin/hello"]

