FROM ghcr.io/anomalyco/opencode:1.2.27 as opencode
FROM ubuntu:24.04

COPY --from=opencode /usr/local/bin/opencode /usr/local/bin/opencode

USER root
RUN apt update -y && \
    apt install -y git jq python3 curl coreutils procps && \
    curl -LsSf https://astral.sh/uv/install.sh | sh && \
    mv /root/.local/bin/uv /usr/local/bin/uv && \
    mv /root/.local/bin/uvx /usr/local/bin/uvx &&
    rm -rf /var/lib/apt/lists/*
