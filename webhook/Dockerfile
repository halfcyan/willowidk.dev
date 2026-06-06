FROM alpine:3.20

RUN apk add --no-cache curl docker-cli
RUN curl -sL https://github.com/adnanh/webhook/releases/download/2.8.0/webhook-linux-amd64.tar.gz \
    | tar xz -C /usr/local/bin --strip-components=1

WORKDIR /opt/webhook
COPY hooks.json .

EXPOSE 9000

CMD ["webhook", "-hooks", "hooks.json", "-verbose", "-port", "9000"]

