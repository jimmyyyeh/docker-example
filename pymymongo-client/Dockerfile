FROM ubuntu:18.04
LABEL maintainer="Jimmy Yeh <chienfeng0719@hotmail.com>"

# from slove python3.6 encoding error
ENV LANG=C.UTF-8

RUN apt update && apt install -y mysql-client mongodb-clients software-properties-common
RUN add-apt-repository ppa:deadsnakes/ppa
RUN apt install -y python3-pip vim
