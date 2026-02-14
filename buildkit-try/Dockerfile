# syntax=docker/dockerfile:1
# 👆 この1行目を書くことで、最新のBuildKitの機能が確実に有効になるよ！

FROM ubuntu:latest

# 💡 ここがBuildKitの魔法！aptのキャッシュディレクトリを一時的にマウントする
RUN rm -f /etc/apt/apt.conf.d/docker-clean; echo 'Binary::apt::APT::Keep-Downloaded-Packages "true";' > /etc/apt/apt.conf.d/keep-cache
RUN --mount=type=cache,target=/var/cache/apt,sharing=locked \
    --mount=type=cache,target=/var/lib/apt \
    apt-get update && apt-get install -y gcc make git