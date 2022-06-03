FROM nfcore/base:1.9

LABEL software="CLRC - Mapping module"
LABEL description="Mapping programs for CLRC"
LABEL version="1.0"
LABEL samtools.version="1.15.1"
LABEL minimap2.version="2.24"
LABEL bwa.version="0.7.17"
LABEL ngmlr.version="0.2.7"
LABEL winnowmap.version="2.03"
LABEL maintainer="Tuan Nguyen"
LABEL maintainer.email="tuan.nguyen@agriculture.vic.gov.au"

COPY clrc_mapping.yml /

SHELL ["/bin/bash", "--login", "-c"]

RUN conda env create -f /clrc_mapping.yml && conda clean -a

RUN conda activate clrc_mapping_env

ENV PATH /opt/conda/envs/clrc_mapping_env/bin:$PATH
