FROM golang:latest AS builder

LABEL maintainer="Paulo Sarmento"

WORKDIR /usr/src/app
COPY . .
RUN CGO_ENABLED=0 GOOS=linux go build -ldflags="-s -w" -o server main.go

#Final stage
FROM scratch
USER 1001
COPY --from=builder /usr/src/app/server /server
ENTRYPOINT [ "./server" ]

