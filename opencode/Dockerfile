FROM ubuntu:24.04

ARG OPENCODE_VERSION=v1.2.27

WORKDIR /tmp

USER root
RUN apt update -y && \
    apt install -y git jq python3 curl coreutils procps wget && \
    curl -LsSf https://astral.sh/uv/install.sh | sh && \
    mv /root/.local/bin/uv /usr/bin/uv && \
    mv /root/.local/bin/uvx /usr/bin/uvx && \
    wget https://github.com/anomalyco/opencode/releases/download/${OPENCODE_VERSION}/opencode-linux-x64.tar.gz && \
    tar xf opencode-linux-x64.tar.gz && rm -rf opencode-linux-x64.tar.gz && \
    mv opencode /usr/bin/opencode && \
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash && \
    bash -c "nvm install 24" && \
    rm -rf /var/lib/apt/lists/*
