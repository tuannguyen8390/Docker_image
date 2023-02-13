FROM continuumio/miniconda3:latest
LABEL software="Jasmine"
LABEL version="1.1.5"
LABEL github_repo="https://github.com/mkirsche/Jasmine"

SHELL ["/bin/bash", "--login", "-c"]

RUN conda config --add channels bioconda
RUN conda config --add channels conda-forge
RUN conda install jasminesv
