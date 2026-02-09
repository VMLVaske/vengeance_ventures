FROM node:22

ARG HUGO_VERSION=0.145.0
ARG GO_VERSION=1.24

RUN apt-get update && \
    apt-get install -y ca-certificates openssl git curl && \
    rm -rf /var/lib/apt/lists/*

# Download and install Hugo
RUN ARCH=$(uname -m) && \
    if [ "$ARCH" = "aarch64" ]; then ARCH=arm64; else ARCH=amd64; fi && \
    curl -LO https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_extended_${HUGO_VERSION}_linux-${ARCH}.tar.gz && \
    tar xf hugo_extended_${HUGO_VERSION}_linux-${ARCH}.tar.gz && \
    mv hugo /usr/bin/hugo && \
    rm hugo_extended_${HUGO_VERSION}_linux-${ARCH}.tar.gz

# Download and install Go
RUN ARCH=$(uname -m) && \
    if [ "$ARCH" = "aarch64" ]; then ARCH=arm64; else ARCH=amd64; fi && \
    curl -LO https://dl.google.com/go/go${GO_VERSION}.linux-${ARCH}.tar.gz && \
    tar -C /usr/local -xzf go${GO_VERSION}.linux-${ARCH}.tar.gz && \
    rm go${GO_VERSION}.linux-${ARCH}.tar.gz

ENV PATH=$PATH:/usr/local/go/bin
