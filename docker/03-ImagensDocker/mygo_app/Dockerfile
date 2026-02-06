FROM golang:latest AS builder

LABEL maintainer="Paulo Sarmento"
LABEL env="production"

WORKDIR /usr/src/app
COPY . .
RUN CGO_ENABLED=0 GOOS=linux go build -ldflags="-s -w" -o server main.go
#FIXO
ENTRYPOINT [ "./server" ]
# Varia posso colocar no comando 
# CMD [ "8080" ]

# # Final stage
# FROM scratch
# USER 1001
# COPY --from=builder /usr/src/app/server /server
