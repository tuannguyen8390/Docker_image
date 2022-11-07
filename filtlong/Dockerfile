FROM ubuntu:18.04

LABEL software="CLRC - Filtlong module"
LABEL description="Filtlong module"
LABEL version="0.2.1"
LABEL maintainer="Tuan Nguyen"
LABEL maintainer.email="tuan.nguyen@agriculture.vic.gov.au"

RUN apt-get update && apt-get install git zlib1g zlib1g-dev wget tar gcc g++ make autoconf bash -y

RUN git clone https://github.com/lh3/seqtk && cd seqtk && make && cd .. 

RUN git clone https://github.com/rrwick/Filtlong.git && cd Filtlong && make -j && bin/filtlong -h

ENV PATH=$PATH:/Filtlong/bin
ENV PATH=$PATH:/seqtk

