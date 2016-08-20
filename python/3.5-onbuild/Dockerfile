FROM elnomade/python:3.5
ENV REFRESHED_AT 2016-08-19

MAINTAINER Leonardo Luduena <lleo@linux.com>

RUN mkdir -p /opt/pyapp
WORKDIR /opt/pyapp

ONBUILD COPY requirements.txt /opt/pyapp/
ONBUILD RUN pip install --no-cache-dir -r requirements.txt

ONBUILD COPY . /opt/pyapp
