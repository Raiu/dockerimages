FROM debian:stable

RUN apt-get update && apt-get install --no-install-recommends --yes \
    curl \
    sudo \
    ca-certificates

ARG USER="kody"

RUN useradd --create-home --shell /bin/bash ${USER}
RUN echo "${USER} ALL=(ALL:ALL) NOPASSWD: ALL" >> /etc/sudoers

USER ${USER}
WORKDIR /home/${USER}