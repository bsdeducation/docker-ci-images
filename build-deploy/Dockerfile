FROM node:16-bullseye

# install aws cli and eb cli and get versions to confirm install

RUN pip3 install --upgrade --no-cache-dir awscli awsebcli

RUN node -v \
    && npm -v \
    && yarn -v \
    && aws --version \
    && eb --version
