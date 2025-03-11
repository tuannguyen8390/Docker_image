FROM continuumio/miniconda3:latest
ENV DEBIAN_FRONTEND=noninteractive 
ENV PATH="/root/miniconda3/bin:${PATH}"
ARG PATH="/root/miniconda3/bin:${PATH}"

LABEL software="CLRC - Sniffles2 module"
LABEL description="Sniffles2 module"
LABEL version="2.6.0"
LABEL maintainer="Tuan Nguyen"
LABEL maintainer.email="tuan.nguyen@agriculture.vic.gov.au"

RUN apt-get update && apt-get install python3-pip libbz2-dev liblzma-dev -y

RUN conda install -c bioconda htslib

RUN pip install sniffles==2.6.0
