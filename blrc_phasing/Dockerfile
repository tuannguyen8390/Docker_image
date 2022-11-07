FROM nfcore/base:1.9

LABEL software="BLRC - Phasing module"
LABEL description="Phasing programs for CLRC"
LABEL version="1.0"
LABEL LongPhase.version="1.15.1"
LABEL HTSLIB="1.16"
LABEL BCFTools="1.16"
LABEL maintainer="Tuan Nguyen"
LABEL maintainer.email="tuan.nguyen@agriculture.vic.gov.au"

COPY clrc_phasing.yml /

SHELL ["/bin/bash", "--login", "-c"]

RUN conda env create -f /clrc_phasing.yml && conda clean -a

RUN conda activate clrc_phasing_env

WORKDIR /
RUN apt-get update && apt-get install git wget tar gcc g++ make autoconf bash -y
RUN git clone https://github.com/twolinin/longphase.git
WORKDIR /longphase
RUN autoreconf -i && ./configure && make -j 4
COPY ./longphase /opt/conda/envs/clrc_phasing_env/bin

ENV PATH /opt/conda/envs/clrc_phasing_env/bin:$PATH
