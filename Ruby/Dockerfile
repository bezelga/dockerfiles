FROM ubuntu

# update
RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update

RUN apt-get install -y build-essential libssl-dev libreadline-dev wget && apt-get clean

# Install ruby-build
RUN apt-get install -y git-core && apt-get clean
RUN git clone https://github.com/sstephenson/ruby-build.git && cd ruby-build && ./install.sh

# install ruby 2.1.1
ENV CONFIGURE_OPTS --disable-install-rdoc
RUN ruby-build 2.1.1 /usr/local
RUN gem install bundler
