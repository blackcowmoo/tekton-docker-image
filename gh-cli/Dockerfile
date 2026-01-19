FROM alpine:3.23.2

RUN apk add --no-cache curl && cd /tmp && \
    curl -L https://github.com/cli/cli/releases/download/v2.85.0/gh_2.85.0_linux_amd64.tar.gz -o gh_2.85.0_linux_amd64.tar.gz && \
    tar xf gh_2.85.0_linux_amd64.tar.gz && \
    mv gh_2.85.0_linux_amd64/bin/gh /usr/local/bin/gh && \
    chmod +x /usr/local/bin/gh && \
    rm -rf gh_2.85.0_linux_amd64.tar.gz gh_2.85.0_linux_amd64 /var/cache/apk/*
