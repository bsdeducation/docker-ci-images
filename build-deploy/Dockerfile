FROM amazonlinux

RUN yum install -y gcc-c++ make

RUN curl -sL https://rpm.nodesource.com/setup_14.x | bash -

RUN yum install -y nodejs python3-pip

RUN pip3 install --upgrade awscli awsebcli

RUN npm install yarn -g
