FROM ubuntu:24.04

ARG OPENCODE_VERSION=v1.17.11

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
    curl -fsSL https://deb.nodesource.com/setup_24.x | bash - && \
    apt update -y && apt install -y nodejs && \
    curl -L https://github.com/rust-lang/rust-analyzer/releases/latest/download/rust-analyzer-x86_64-unknown-linux-gnu.gz | gunzip -c - > /usr/local/bin/rust-analyzer && \
    chmod +x /usr/local/bin/rust-analyzer && \
    curl https://sh.rustup.rs -sSf | sh -s -- -y && \
    ln -sf /root/.cargo/bin/cargo /usr/bin/cargo && \
    rm -rf /var/lib/apt/lists/*
