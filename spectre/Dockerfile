FROM continuumio/miniconda3:latest
ARG conda_env=spectre-env

LABEL software="Spectre"
LABEL description="CNV for long-read sequencing"
LABEL version="1.0"
LABEL maintainer="Tuan Nguyen"
LABEL maintainer.email="tuan.nguyen@agriculture.vic.gov.au"

COPY spectre.yml /
SHELL ["/bin/bash", "--login", "-c"]
RUN conda env create -f /spectre.yml && conda clean -a
RUN git clone https://github.com/fritzsedlazeck/Spectre
WORKDIR /Spectre

ENV PATH /opt/conda/envs/spectre-env/bin:$PATH
RUN echo "source activate ${conda_env}" > ~/.bashrc
