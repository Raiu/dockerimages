FROM alpine:latest

RUN apk add -y --no-cache dropbear sudo bash curl

ARG USER="kody"
RUN adduser -D -g '' ${USER}

ARG NOPASSWD=true
RUN if [ "${NOPASSWD}" = "true" ] ; then echo "${USER} ALL=(ALL:ALL) NOPASSWD: ALL" >> /etc/sudoers ; fi

USER ${USER}

ARG APP="/home/${USER}"
WORKDIR ${APP}