FROM continuumio/miniconda3:4.12.0
ENV DEBIAN_FRONTEND noninteractive

LABEL software="CLRC - Filtlong module"
LABEL description="Filtlong module"
LABEL version="0.2.1"
LABEL maintainer="Tuan Nguyen"
LABEL maintainer.email="tuan.nguyen@agriculture.vic.gov.au" 

RUN apt-get update && apt-get install git zlib1g zlib1g-dev libbz2-dev liblzma-dev wget tar gcc g++ make autoconf locales bash -y

RUN git clone https://github.com/lh3/seqtk && cd seqtk && make && cd .. 
RUN git clone https://github.com/rrwick/Filtlong.git && cd Filtlong && make -j && bin/filtlong -h

RUN git clone https://github.com/samtools/htslib && cd htslib && git submodule update --init --recursive && autoreconf -i && ./configure && make && cd .. 
ENV PATH=$PATH:/Filtlong/bin
ENV PATH=$PATH:/Filtlong/htslib
ENV PATH=$PATH:/seqtk
ENV PATH=$PATH:/htslib

RUN pip3 install --upgrade cython
RUN pip3 install --upgrade NanoPlot

RUN conda config --add channels conda-forge
RUN conda config --add channels bioconda
RUN conda install porechop_abi=0.5.0



