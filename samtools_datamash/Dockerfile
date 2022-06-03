FROM nfcore/base:1.9

LABEL software="CLRC - Samtools/Datamash module"
LABEL description="Samtools/Datamash module"
LABEL version="1.0"
LABEL samtools.version="1.15.1"
LABEL datamash.version="1.7"
LABEL maintainer="Tuan Nguyen"
LABEL maintainer.email="tuan.nguyen@agriculture.vic.gov.au"

COPY samtools-datamash.yml /

SHELL ["/bin/bash", "--login", "-c"]

RUN conda env create -f /samtools-datamash.yml && conda clean -a

RUN conda activate samtools-datamash-env

ENV PATH /opt/conda/envs/samtools-datamash-env/bin:$PATH
