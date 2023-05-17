FROM nfcore/base:1.9

LABEL software="CLRC - mosdepth module"
LABEL description="mosdepth module"
LABEL version="1.0"
LABEL mosdepth.version="0.0.3"
LABEL maintainer="Tuan Nguyen"
LABEL maintainer.email="tuan.nguyen@agriculture.vic.gov.au"

COPY mosdepth.yml /

SHELL ["/bin/bash", "--login", "-c"]

RUN conda env create -f /mosdepth.yml && conda clean -a

RUN conda activate mosdepth-env

ENV PATH /opt/conda/envs/mosdepth-env/bin:$PATH
