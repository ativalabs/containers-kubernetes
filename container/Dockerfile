
# Build Stage

FROM golang:1.21-alpine AS BuildStage

WORKDIR /build

COPY . .

RUN go build -o /build/test main.go

# Deploy Stage

FROM alpine:latest

WORKDIR /app

COPY --from=BuildStage /build/test /app/test

EXPOSE 8000

USER nobody

ENTRYPOINT ["/app/test"]



