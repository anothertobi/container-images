FROM docker.io/library/ubuntu:23.10@sha256:93c55b20cc3b34b0492ea90fe2fad93f1dfba56005bb56ba9bcc3f83d6495c16

ARG TARGETPLATFORM=linux/arm64
# renovate: datasource=github-releases depName=gohugoio/hugo
ARG GOHUGO_VERSION=v0.113.0

WORKDIR /app

RUN apt-get update && apt-get install -y \
    wget && \
        wget https://github.com/gohugoio/hugo/releases/download/${GOHUGO_VERSION}/hugo_${GOHUGO_VERSION#v}_linux-${TARGETPLATFORM#linux/}.tar.gz \
    -O hugo.tar.gz && \
    tar xf hugo.tar.gz -C /usr/local/bin/ && \
    rm hugo.tar.gz && \
    apt-get remove -y wget && \
    rm -rf /var/lib/apt/lists/*
