FROM continuumio/miniconda3:latest

LABEL software="Spectre"
LABEL description="CNV for long-read sequencing"
LABEL version="1.0"
LABEL maintainer="Tuan Nguyen"
LABEL maintainer.email="tuan.nguyen@agriculture.vic.gov.au"

SHELL ["/bin/bash", "--login", "-c"]

RUN conda config --add channels conda-forge
RUN conda config --add channels bioconda
RUN conda install pysam==0.21.0 numpy==1.24.3 pandas==2.0.1 matplotlib==3.7.1 scipy==1.10.1

RUN git clone https://github.com/fritzsedlazeck/Spectre
WORKDIR /Spectre
RUN cp spectre.py /usr/local/bin/

