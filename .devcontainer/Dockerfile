# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.183.0/containers/ubuntu/.devcontainer/base.Dockerfile

# [Choice] Ubuntu version: bionic, focal
ARG VARIANT="focal"
FROM mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}

RUN export DEBIAN_FRONTEND=noninteractive && apt-get update

# install dependencies
RUN apt-get install --yes --no-install-recommends \
        libdbus-1-dev \
        libglew-dev \
        libgtk2.0-dev \
        libudev-dev

# install build essentials
RUN apt-get install --yes --no-install-recommends \
    ccache \
    cmake \
    g++-9 \
    gcc-9 \
    m4 \
    make \
    ninja-build

RUN update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-9 10 \
    && update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-9 10

# install used for conan
RUN apt-get install --yes --no-install-recommends \
    python3 \
    python3-pip

RUN pip3 install conan

RUN unset DEBIAN_FRONTEND
