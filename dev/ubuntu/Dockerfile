FROM ubuntu:22.04

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get upgrade --yes && apt-get install --no-install-recommends --yes \
    apt-utils ca-certificates ssh sudo curl

ARG USER="kody"
RUN useradd --create-home --shell /bin/bash ${USER}

ARG NOPASSWD=true
RUN if [ "${NOPASSWD}" = "true" ] ; then echo "${USER} ALL=(ALL:ALL) NOPASSWD: ALL" >> /etc/sudoers ; fi

USER ${USER}

ARG APP="/home/${USER}"
WORKDIR ${APP}