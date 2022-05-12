FROM ubuntu:18.04

COPY CLRC.yml /

SHELL ["/bin/bash", "--login", "-c"]

RUN conda env create -f /CLRC.yml && conda clean -a

RUN conda activate CLRC-env

ENV PATH /opt/conda/envs/CLRC-env/bin:$PATH
