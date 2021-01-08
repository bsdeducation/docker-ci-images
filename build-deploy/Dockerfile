FROM ubuntu:20.10

# node, npm (to get source and install deps)
RUN apt-get update && apt-get -y install sudo nodejs npm git python3-pip curl

# aws, eb (for deployment)
RUN pip3 install --upgrade awscli awsebcli

# yarn (install deps and run tasks)
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
RUN sudo apt-get update && sudo apt-get install -y yarn

# python (for node-gyp during install)
RUN sudo apt-get install -y python2
ENV PYTHON /usr/bin/python2