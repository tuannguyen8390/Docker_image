FROM continuumio/miniconda3:latest
LABEL software="Jasmine"
LABEL version="1.1.5"
LABEL github_repo="https://github.com/mkirsche/Jasmine"
LABEL software="CLRC - Jasmine module"
LABEL maintainer="Tuan Nguyen"
LABEL maintainer.email="tuan.nguyen@agriculture.vic.gov.au"

SHELL ["/bin/bash", "--login", "-c"]

RUN conda config --add channels bioconda
RUN conda config --add channels conda-forge
RUN conda install jasminesv
