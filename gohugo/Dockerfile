FROM docker.io/library/ubuntu:23.10@sha256:8abf9cea172b86fe77d65ef1abbdb186d06d1b44858efe09a16de7e2c43f645a

ARG TARGETPLATFORM=linux/arm64
# renovate: datasource=github-releases depName=gohugoio/hugo
ARG GOHUGO_VERSION=v0.115.3

WORKDIR /app

RUN apt-get update && apt-get install -y \
    wget && \
        wget https://github.com/gohugoio/hugo/releases/download/${GOHUGO_VERSION}/hugo_${GOHUGO_VERSION#v}_linux-${TARGETPLATFORM#linux/}.tar.gz \
    -O hugo.tar.gz && \
    tar xf hugo.tar.gz -C /usr/local/bin/ && \
    rm hugo.tar.gz && \
    apt-get remove -y wget && \
    rm -rf /var/lib/apt/lists/*
