FROM ubuntu:16.04

RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak
COPY sources.list /etc/apt/sources.list
COPY ./client /client
WORKDIR /client

RUN apt-get update && \
    apt-get -y upgrade && \
    apt-get install -y iptables && \
    apt-get install -y python3 && \
    apt-get install -y python3-pip && \
    pip3 install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple && \
    chmod a+x start.sh

EXPOSE 5000
