# Brief reminder how to use this one
#
# docker build -t="aosp6-trusty" .
# docker run -t -i -v $PWD/src:/work aosp6-trusty
# docker container prune
# docker image rm aosp6-trusty


FROM ubuntu:14.04
MAINTAINER Alexey Roslyakov <alexey.roslyakov@gmail.com>

# update packages list and install dependencies
RUN apt-get update ; \
    apt-get install -y git-core gnupg flex bison gperf build-essential zip curl \
    zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386 lib32ncurses5-dev \
    x11proto-core-dev libx11-dev lib32z-dev ccache libgl1-mesa-dev libxml2-utils \
    xsltproc unzip \
    python genisoimage bc wget


# For Android7+ -- download and install OpenJDK8
#RUN cd /tmp; wget -c http://archive.ubuntu.com/ubuntu/pool/universe/o/openjdk-8/openjdk-8-jre-headless_8u45-b14-1_amd64.deb ; \
#    wget -c http://archive.ubuntu.com/ubuntu/pool/universe/o/openjdk-8/openjdk-8-jre_8u45-b14-1_amd64.deb ; \
#    wget -c http://archive.ubuntu.com/ubuntu/pool/universe/o/openjdk-8/openjdk-8-jdk_8u45-b14-1_amd64.deb ; \
#    dpkg -i openjdk-8-jre-headless_8u45-b14-1_amd64.deb openjdk-8-jre_8u45-b14-1_amd64.deb openjdk-8-jdk_8u45-b14-1_amd64.deb

#
# For Android 5-6: install OpenJDK7
#
RUN sudo apt-get install -y openjdk-7-jdk

#
# Configure java and javac, create a working directory
#
RUN update-alternatives --config java ; \
    update-alternatives --config javac ; \
    mkdir -p /work
