FROM ubuntu:latest
MAINTAINER Dipesh P 

RUN apt-get update && apt-get install -y vim \
  curl \
  nmap \
  telnet
RUN apt-get install -y openssh-client
RUN apt-get install -y openssh-server
RUN gpg --keyserver hkp://keys.gnupg.net --recv-keys D39DC0E3
RUN curl -sSL https://get.rvm.io | bash -s stable
RUN echo 'source /etc/profile.d/rvm.sh' >> ~/.bashrc
RUN /bin/bash -l -c "rvm requirements"
RUN /bin/bash -l -c "rvm install 2.1.2"
RUN /bin/bash -l -c "rvm use 2.1.2 --default"
RUN /bin/bash -l -c "mkdir dipesh"
ADD test.rb /dipesh/
WORKDIR /dipesh
RUN /bin/bash -l -c "ruby test.rb"


