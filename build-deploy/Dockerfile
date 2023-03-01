FROM node:16-bullseye

# Install python and pip3
RUN apt-get update \
    && apt-get -y install awscli python3 git python3-pip \
    && rm -rf /var/lib/apt/lists/*

# install aws cli and eb cli
RUN pip3 install --upgrade --no-cache-dir awsebcli

# Print versions to confirm install
RUN node -v \
    && npm -v \
    && yarn -v \
    && aws --version \
    && eb --version
