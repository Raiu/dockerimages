FROM alpine:latest

RUN apk add -y --no-cache curl sudo

ARG USER="kody"

RUN adduser -D -g '' ${USER}
RUN echo "${USER} ALL=(ALL:ALL) NOPASSWD: ALL" >> /etc/sudoers

USER ${USER}
WORKDIR /home/${USER}