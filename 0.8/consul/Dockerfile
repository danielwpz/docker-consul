FROM alpine:3.4

ENV CONSUL_VERSION 0.8.5
ENV CONSUL_SHA256 35dc317c80862c306ea5b1d9bc93709483287f992fd0797d214d1cc1848e7b62

RUN apk --no-cache add curl ca-certificates \
    && curl -sSL https://releases.hashicorp.com/consul/${CONSUL_VERSION}/consul_${CONSUL_VERSION}_linux_amd64.zip -o /tmp/consul.zip \
    && echo "${CONSUL_SHA256}  /tmp/consul.zip" > /tmp/consul.sha256 \
    && sha256sum -c /tmp/consul.sha256 \
    && cd /bin \
    && unzip /tmp/consul.zip \
    && chmod +x /bin/consul \
    && rm /tmp/consul.zip

ENTRYPOINT ["/bin/consul"]
