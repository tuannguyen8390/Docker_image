FROM continuumio/miniconda3:latest
ENV DEBIAN_FRONTEND=noninteractive 

LABEL software="CLRC - CuteSV module"
LABEL description="CuteSV module"
LABEL version="2.0.3"
LABEL maintainer="Tuan Nguyen"
LABEL maintainer.email="tuan.nguyen@agriculture.vic.gov.au"
LABEL github_repo="https://github.com/tjiangHIT/cuteSV"

RUN conda config --add channels conda-forge
RUN conda config --add channels bioconda
RUN conda install cutesv tabix
