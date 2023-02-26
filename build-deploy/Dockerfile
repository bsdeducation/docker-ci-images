FROM ubuntu:22.04

# node, npm (to get source and install deps)
RUN apt-get update \
    && apt-get -y install sudo curl \
    && curl -sL https://deb.nodesource.com/setup_16.x | bash - \
    && apt-get -y install sudo nodejs \
    && node -v \
    && npm -v \
    && rm -rf /var/lib/apt/lists/*
