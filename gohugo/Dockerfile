FROM docker.io/library/ubuntu:23.10@sha256:bd1e0eb3171a6e499c84211e73c4f5f5b2a585507256f772f5c4f4420a3d8591

ARG TARGETPLATFORM=linux/arm64
# renovate: datasource=github-releases depName=gohugoio/hugo
ARG GOHUGO_VERSION=v0.114.0

WORKDIR /app

RUN apt-get update && apt-get install -y \
    wget && \
        wget https://github.com/gohugoio/hugo/releases/download/${GOHUGO_VERSION}/hugo_${GOHUGO_VERSION#v}_linux-${TARGETPLATFORM#linux/}.tar.gz \
    -O hugo.tar.gz && \
    tar xf hugo.tar.gz -C /usr/local/bin/ && \
    rm hugo.tar.gz && \
    apt-get remove -y wget && \
    rm -rf /var/lib/apt/lists/*
