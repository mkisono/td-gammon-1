FROM ubuntu:20.04

ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get install -y \
    gnubg \
    git \
    curl \
    python3-dev

RUN curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py && python3 get-pip.py

WORKDIR /build
RUN git clone https://github.com/dellalibera/gym-backgammon.git
RUN cd gym-backgammon && pip3 install -e .

COPY requirements.txt /build/requirements.txt
RUN pip3 install -r requirements.txt
