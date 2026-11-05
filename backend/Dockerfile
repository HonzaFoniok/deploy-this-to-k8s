FROM golang:1.27.1 AS builder

WORKDIR /app

COPY go.mod go.sum ./

RUN go mod download

COPY . .

RUN CGO_ENABLED=0 go build -o backend-app

FROM alpine:latest

WORKDIR /app

COPY --from=builder /app/backend-app .

CMD ["./backend-app"]
