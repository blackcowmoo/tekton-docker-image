FROM ghcr.io/anomalyco/opencode:1.2.27 as opencode
FROM ubuntu:24.04

USER root
RUN apt update -y && \
    apt install -y git jq python3 curl coreutils procps && \
    curl -LsSf https://astral.sh/uv/install.sh | sh && \
    mv /root/.local/bin/uv /usr/bin/uv && \
    mv /root/.local/bin/uvx /usr/bin/uvx && \
    rm -rf /var/lib/apt/lists/*

COPY --from=opencode /usr/local/bin/opencode /usr/bin/opencode
