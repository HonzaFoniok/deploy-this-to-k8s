FROM golang:1.27.1 AS builder

WORKDIR /app

COPY go.mod go.sum ./

RUN go mod download

COPY . .

RUN CGO_ENABLED=0 go build -o frontend-app

FROM alpine:latest

WORKDIR /app

COPY --from=builder /app/frontend-app .

CMD ["./frontend-app"]
