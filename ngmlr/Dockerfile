FROM nfcore/base:1.9

COPY ngmlr.yml /

SHELL ["/bin/bash", "--login", "-c"]

RUN conda env create -f /ngmlr.yml && conda clean -a

RUN conda activate ngmlr-env

ENV PATH /opt/conda/envs/ngmlr-env/bin:$PATH
