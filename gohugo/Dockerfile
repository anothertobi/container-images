FROM docker.io/library/ubuntu:23.04@sha256:dbc0706ea4ddf6cade6230e0c73bbce2e1028f1cb855e0203d031d43e4037958

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
