FROM golang:1.26.1-alpine

WORKDIR /app

RUN apk add --no-cache git

COPY go.mod go.sum ./
RUN go mod download

COPY . .

RUN go build -tags embed -o main ./cmd/server/

EXPOSE 8080

CMD ["./main"]
