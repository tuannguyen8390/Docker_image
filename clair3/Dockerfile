FROM ubuntu:18.04

COPY clair3.yml /

SHELL ["/bin/bash", "--login", "-c"]

RUN conda env create -f /clair3.yml && conda clean -a

RUN conda activate clair3-env

ENV PATH /opt/conda/envs/clair3-env/bin:$PATH
