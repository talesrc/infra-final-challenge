FROM golang:1.22-rc-alpine3.18 as builder

WORKDIR /app

COPY go.mod main.go .

RUN go build -o static-server

FROM alpine:3.19

RUN addgroup -g 430 wsuser && \
    adduser -u 1000 --disabled-password -G wsuser wsuser

USER wsuser

WORKDIR /app

RUN mkdir static && \
    chown wsuser:wsuser static && \
    chmod 750 static /app

COPY --chown=wsuser:wsuser --chmod=750 static/ static/

COPY --from=builder --chown=wsuser:wsuser --chmod=750 /app/static-server .

CMD ["/app/static-server"]
