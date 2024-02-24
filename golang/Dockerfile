FROM golang:alpine3.19 as builder
COPY hello /home/hello
WORKDIR /home/hello
RUN CGO_ENABLED=0 go build -o .

FROM scratch
WORKDIR /home/hello
COPY --from=builder /home/hello /home/hello
CMD ["./hello" ]