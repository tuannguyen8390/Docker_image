FROM ubuntu:jammy
ENV DEBIAN_FRONTEND noninteractive

LABEL software="CLRC - Dorado Basecaller module"
LABEL description="Dorado Basecaller module"
LABEL version="0.3.1"
LABEL maintainer="Tuan Nguyen"
LABEL maintainer.email="tuan.nguyen@agriculture.vic.gov.au" 

RUN apt-get update && apt-get install --no-install-recommends -y \
        curl \
        git \
        ca-certificates \
        build-essential \
        nvidia-cuda-toolkit \
        libhdf5-dev \
        libssl-dev \
        libzstd-dev \
        python3.9 \
        gcc-9 \
        cmake \
        autoconf \
        automake

RUN git clone https://github.com/nanoporetech/dorado.git 
RUN chmod -R 777 dorado
RUN cd dorado && cmake -S . -B cmake-build 
RUN cmake --build cmake-build --config Release -j 
RUN ctest --test-dir cmake-build

ENV PATH=$PATH:./cmake-build/bin/dorado
