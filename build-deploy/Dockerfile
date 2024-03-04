FROM node:18-bookworm

# Install python and pip3 and Java (for the Python AST in expectations package)
RUN apt-get update \
    && apt-get -y install awscli python3 python3-pip default-jre \
    && rm -rf /var/lib/apt/lists/*

# install aws cli and eb cli
RUN pip3 install --upgrade --no-cache-dir awsebcli --break-system-packages

# Print versions to confirm install
RUN node -v \
    && npm -v \
    && yarn -v \
    && aws --version \
    && eb --version \
    && java --version
