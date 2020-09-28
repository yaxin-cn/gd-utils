FROM node:14.11-stretch-slim as builder

RUN set -ex \
    && apt-get update \
    && apt-get install -y git gcc make python3 g++ \
    && git clone https://github.com/yaxin-cn/gd-utils /app \
    && cd /app \
    && npm i



FROM node:14.11-stretch-slim

COPY --from=builder /app /app

WORKDIR /app

CMD ["/usr/local/bin/node", "/app/server.js"]
