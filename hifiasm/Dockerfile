FROM continuumio/miniconda3:latest

LABEL description="Miniasm"

RUN apt-get update && apt-get install git zlib1g zlib1g-dev libbz2-dev liblzma-dev wget tar gcc g++ make autoconf locales python3-pip bash -y

RUN git clone https://github.com/xfengnefx/hifiasm-meta.git
RUN cd hifiasm-meta && make

ENV PATH /hifiasm-meta/:$PATH