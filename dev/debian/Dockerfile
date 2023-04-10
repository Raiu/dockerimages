FROM debian:stable

RUN DEBIAN_FRONTEND=noninteractive apt-get update && apt-get install --no-install-recommends --yes \
    apt-utils \
    ca-certificates \
    curl \
    sudo

ARG USER="kody"

RUN useradd --create-home --shell /bin/bash ${USER}
RUN echo "${USER} ALL=(ALL:ALL) NOPASSWD: ALL" >> /etc/sudoers

USER ${USER}
WORKDIR /home/${USER}