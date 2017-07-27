FROM microsoft/vsts-agent:ubuntu-16.04-standard
MAINTAINER Nagaraju KLV <klvnraju@gmail.com>


RUN apt-get update \
    && apt-get install -y --no-install-recommends python-pip python-dev build-essential python-setuptools

RUN pip install --upgrade pip

RUN pip install -U platformio