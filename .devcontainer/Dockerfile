# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.145.1/containers/javascript-node/.devcontainer/base.Dockerfile

FROM ubuntu:20.10

# Upgrade Packages
RUN DEBIAN_FRONTEND=noninteractive \
  && apt-get -y update \
  && apt-get -y upgrade

# Install Pre-Reqs
RUN apt-get install -y curl wget git \
  && apt-get install -y apt-utils \
  && apt-get install -y build-essential \
  && apt-get install -y libnss3-dev \
  && apt-get install -y wget gnupg ca-certificates \
  && apt-get install -y iputils-ping \
  && apt-get install -y apt-transport-https \
  && apt-get install -y postgresql-client

# Install Zsh
# Uses "dracula" (better on the eyes) theme, with no plugins
RUN sh -c "$(wget -O- https://github.com/deluan/zsh-in-docker/releases/download/v1.1.1/zsh-in-docker.sh)" -- \
  -t af-magic

# Install Docker Tools
RUN apt-get install -y docker-compose

# Install NodeJs and npm
RUN apt-get install -y nodejs \
  && apt-get install -y npm

# Install pip
RUN alias python=python3 \
  && apt-get install -y python3-pip

# Install dotnet
RUN curl -sSL https://dot.net/v1/dotnet-install.sh -o ./dotnet-install.sh \
  && chmod +x ./dotnet-install.sh \
  && ./dotnet-install.sh --version 3.1.401 \
  && rm ./dotnet-install.sh

ENV PATH "/root/.dotnet:${PATH}"
