FROM golang:1.21 as builder
WORKDIR /app
COPY . .
RUN CGO_ENABLED=0 GOOS=linux go build -o /go-app

FROM alpine:latest
COPY --from=builder /go-app /app/go-app
EXPOSE 8080
CMD ["/app/go-app"]