FROM rajsaxena/ubuntu_14.04_with_basic_utils
MAINTAINER Dipesh P 

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


