FROM docker.io/library/ubuntu:22.10@sha256:a9a425d086dbb34c1b5b99765596e2a3cc79b33826866c51cd4508d8eb327d2b

ARG TARGETPLATFORM=linux/arm64
 # renovate: datasource=github-releases depName=gohugoio/hugo
ARG GOHUGO_VERSION=v0.111.3

WORKDIR /app

RUN apt-get update && apt-get install -y \
    wget && \
        wget https://github.com/gohugoio/hugo/releases/download/${GOHUGO_VERSION}/hugo_${GOHUGO_VERSION#v}_linux-${TARGETPLATFORM#linux/}.tar.gz \
    -O hugo.tar.gz && \
    tar xf hugo.tar.gz -C /usr/local/bin/ && \
    rm hugo.tar.gz && \
    apt-get remove -y wget && \
    rm -rf /var/lib/apt/lists/*
