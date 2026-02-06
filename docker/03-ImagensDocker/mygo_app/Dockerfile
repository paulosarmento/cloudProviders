FROM golang:latest AS builder

WORKDIR /usr/src/app

COPY . .

RUN CGO_ENABLED=0 GOOS=linux go build -ldflags="-s -w" -o server main.go

FROM scratch

COPY --from=builder /usr/src/app/server /server

CMD [ "./server" ]
