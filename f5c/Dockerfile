FROM nfcore/base:1.9

COPY f5c.yml /

SHELL ["/bin/bash", "--login", "-c"]

RUN conda env create -f /f5c.yml && conda clean -a

RUN conda activate f5c-env

ENV PATH /opt/conda/envs/f5c-env/bin:$PATH
