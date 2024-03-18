FROM alpine:3.19

RUN apk add --no-cache dropbear shadow sudo bash curl git wget

ARG BUILD_USER="kody"
ARG BUILD_USER_ID=1000
ARG BUILD_GROUP=${BUILD_USER}
ARG BUILD_GROUP_ID=${BUILD_USER_ID}

ENV USER=kody
ENV USER_ID=1000
ENV GROUP=${USER}
ENV GROUP_ID=${USER_ID}

RUN addgroup -g ${GROUP_ID} ${GROUP} && \
    adduser --shell /bin/bash --disabled-password \
    --uid $USER_ID --ingroup ${GROUP} ${USER}

ARG NOPASSWD=true
RUN if [ "${NOPASSWD}" = "true" ] ; then echo "${USER} ALL=(ALL:ALL) NOPASSWD: ALL" >> /etc/sudoers ; fi

USER ${USER}

RUN git config --global --add safe.directory '*'

ARG APP="/home/${USER}"
WORKDIR ${APP}