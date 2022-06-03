FROM nfcore/base:1.9

LABEL software="CLRC - f5c module"
LABEL description="f5c module - for methylation calling with GPU"
LABEL version="1.0"
LABEL f5c.version="0.8"
LABEL maintainer="Tuan Nguyen"
LABEL maintainer.email="tuan.nguyen@agriculture.vic.gov.au"

COPY f5c.yml /

SHELL ["/bin/bash", "--login", "-c"]

RUN conda env create -f /f5c.yml && conda clean -a

RUN conda activate f5c-env

ENV PATH /opt/conda/envs/f5c-env/bin:$PATH
