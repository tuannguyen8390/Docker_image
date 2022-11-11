FROM continuumio/miniconda3:latest
LABEL software="LongPhase"
LABEL version="1.4"
LABEL github_repo="https://github.com/twolinin/longphase"

SHELL ["/bin/bash", "--login", "-c"]
RUN conda install -c bioconda htslib

RUN apt-get update && apt-get install git gcc g++ make autoconf zlib1g-dev libbz2-dev liblzma-dev bash -y
RUN git clone https://github.com/twolinin/longphase.git
WORKDIR /longphase
RUN autoreconf -i && ./configure && make -j 4
RUN cp longphase /usr/local/bin/