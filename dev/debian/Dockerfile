FROM debian:bullseye

ARG DEBIAN_FRONTEND=noninteractive

COPY sources.list /etc/apt/sources.list
RUN apt-get update && apt-get upgrade --yes && apt-get install --no-install-recommends --yes \
    dialog readline-common apt-utils ca-certificates ssh sudo curl

ARG BUILD_USER="kody"
ARG BUILD_USER_ID=1000
ARG BUILD_GROUP=${BUILD_USER}
ARG BUILD_GROUP_ID=${BUILD_USER_ID}

ENV USER=kody
ENV USER_ID=1000
ENV GROUP=${USER}
ENV GROUP_ID=${USER_ID}

RUN addgroup --gid ${GROUP_ID} ${GROUP} && \
    adduser --shell /bin/bash --disabled-password \
    --uid $USER_ID --ingroup ${GROUP} ${USER}

ARG NOPASSWD=true
RUN if [ "${NOPASSWD}" = "true" ] ; then echo "${USER} ALL=(ALL:ALL) NOPASSWD: ALL" >> /etc/sudoers ; fi

USER ${USER}

ARG APP="/home/${USER}"
WORKDIR ${APP}