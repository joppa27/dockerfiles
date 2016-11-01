FROM centos:7
MAINTAINER Idi Eradiri ieradiri@gmail.com
# docker run -it -v /tmp/.X11-unix/:/tmp/.X11-unix/ -e DISPLAY=$DISPLAY --rm kongkoro/pycharm

ENV PYCHARM_HOME=/etc/pycharm
RUN yum update -y &&\
    yum install -y which wget git java-1.8.0-openjdk python && yum clean all &&\
    wget https://download.jetbrains.com/python/pycharm-community-2016.2.3.tar.gz -O /tmp/pycharm.tar.gz &&\
    mkdir ${PYCHARM_HOME} && tar -xzvf /tmp/pycharm.tar.gz -C ${PYCHARM_HOME} --strip=1 &&\
    wget -P /tmp/ https://bootstrap.pypa.io/get-pip.py && python /tmp/get-pip.py &&\
    rm -rf /var/lib/apt-lists; rm -rf /tmp/*; yum remove wget -y;
	
ENTRYPOINT ["/etc/pycharm/bin/pycharm.sh"]
