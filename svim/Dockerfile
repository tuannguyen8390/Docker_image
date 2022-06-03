FROM nfcore/base:1.9

LABEL software="CLRC - Svim module"
LABEL description="Svim module"
LABEL version="1.0"
LABEL svim.version="1.4.2"
LABEL maintainer="Tuan Nguyen"
LABEL maintainer.email="tuan.nguyen@agriculture.vic.gov.au"

COPY svim.yml /

SHELL ["/bin/bash", "--login", "-c"]

RUN conda env create -f /svim.yml && conda clean -a

RUN conda activate svim-env

ENV PATH /opt/conda/envs/svim-env/bin:$PATH
