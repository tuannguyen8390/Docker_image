FROM nfcore/base:1.9

LABEL software="CLRC - SVs module"
LABEL description="SV modules for CLRC"
LABEL version="1.0"
LABEL maintainer="Tuan Nguyen"
LABEL maintainer.email="tuan.nguyen@agriculture.vic.gov.au"

COPY clrc_sv.yml /

SHELL ["/bin/bash", "--login", "-c"]

RUN conda env create -f /clrc_sv.yml && conda clean -a

RUN conda activate clrc_sv_env

ENV PATH /opt/conda/envs/clrc_sv_env/bin:$PATH
