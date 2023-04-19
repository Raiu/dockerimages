FROM debian:bullseye

ARG DEBIAN_FRONTEND=noninteractive

COPY sources.list /etc/apt/sources.list
RUN apt-get update && apt-get upgrade --yes && apt-get install --no-install-recommends --yes \
    dialog readline-common apt-utils ca-certificates ssh sudo curl

ARG USER="kody"
RUN useradd --create-home --shell /bin/bash ${USER}

ARG NOPASSWD=true
RUN if [ "${NOPASSWD}" = "true" ] ; then echo "${USER} ALL=(ALL:ALL) NOPASSWD: ALL" >> /etc/sudoers ; fi

USER ${USER}

ARG APP="/home/${USER}"
WORKDIR ${APP}