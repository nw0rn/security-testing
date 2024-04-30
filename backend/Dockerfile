FROM golang:latest as builder

WORKDIR /app

COPY . .

RUN go mod download && go build -o main .

FROM ubuntu:latest

WORKDIR /app

COPY --from=builder /app/main .

EXPOSE 8080

CMD ["./main"]
