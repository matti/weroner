FROM ubuntu:22.04

RUN apt-get update && apt-get install -y --no-install-recommends \
  ca-certificates curl libcap2-bin \
  && apt-get clean

RUN curl -sfL -o /usr/local/bin/weron "https://github.com/pojntfx/weron/releases/latest/download/weron.linux-$(uname -m)" \
  && chmod +x /usr/local/bin/weron

ENV PORT=8080
EXPOSE $PORT

WORKDIR /app
COPY app .
ENTRYPOINT [ "/app/entrypoint.sh" ]