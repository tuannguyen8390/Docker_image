FROM continuumio/miniconda3:latest

LABEL software="Spectre"
LABEL description="CNV for long-read sequencing"
LABEL version="1.0"
LABEL maintainer="Tuan Nguyen"
LABEL maintainer.email="tuan.nguyen@agriculture.vic.gov.au"

COPY spectre.yml /
SHELL ["/bin/bash", "--login", "-c"]
RUN conda env create -f /spectre.yml && conda clean -a
RUN apt-get update && apt-get install git gcc g++ make autoconf zlib1g-dev libbz2-dev liblzma-dev bash -y
RUN git clone https://github.com/fritzsedlazeck/Spectre
WORKDIR /Spectre
RUN conda activate spectre
