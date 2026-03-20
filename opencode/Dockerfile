FROM ghcr.io/anomalyco/opencode:1.2.27

RUN apk add git jq python3 curl && \
    curl -LsSf https://astral.sh/uv/install.sh | sh && \
    mv /root/.local/bin/uv /usr/local/bin/uv && \
    mv /root/.local/bin/uvx /usr/local/bin/uvx
