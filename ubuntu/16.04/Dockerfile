FROM ubuntu:16.04
ENV REFRESHED_AT 2017-09-01

MAINTAINER Leonardo Luduena <lleo@linux.com>

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get install apt-utils debconf-utils wget curl nano -y --no-install-recommends && \
    rm -rf /var/lib/apt/lists/*

RUN mkdir -p /opt/ubuntu
ENV HOME /opt/ubuntu
WORKDIR /opt/ubuntu

VOLUME ["/etc", "/var/log"]
