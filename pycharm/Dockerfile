FROM debian:wheezy
MAINTAINER Idi Eradiri ieradiri@gmail.com
# docker run -it -v /tmp/.X11-unix/:/tmp/.X11-unix/ -e DISPLAY=$DISPLAY --rm kongkoro/pycharm

ENV PYCHARM_HOME=/etc/pycharm
RUN apt-get update &&\
    apt-get install -y \
    wget \
    git \
    openjdk-7-jre \
    libxrender1 \
    libxtst6 \
    python \
    --no-install-recommends &&\
    wget -P /tmp/ http://download.jetbrains.com/python/pycharm-community-4.5.4.tar.gz &&\
    mkdir ${PYCHARM_HOME} && tar -xzvf /tmp/pycharm-community-4.5.4.tar.gz -C ${PYCHARM_HOME} --strip=1 &&\
    wget -P /tmp/ https://bootstrap.pypa.io/get-pip.py && python /tmp/get-pip.py &&\
    rm -rf /var/lib/apt-lists; rm -rf /tmp/*; apt-get purge wget -y; apt-get autoremove -y
	
ENTRYPOINT ["/etc/pycharm/bin/pycharm.sh"]
