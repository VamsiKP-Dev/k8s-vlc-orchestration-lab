FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
    vlc \
    vlc-plugin-base \
    vlc-plugin-video-output \
    curl \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

WORKDIR /app
RUN mkdir -p /app/playlists /app/config /app/logs

# Non-root user
RUN useradd -ms /bin/bash vlcuser
RUN chown -R vlcuser:vlcuser /app
USER vlcuser

CMD ["cvlc", "-I", "http", "--http-port=8080", "--no-video-title-show", "--no-audio", "/app/playlists/playlist.m3u"]
