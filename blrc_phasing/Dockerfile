FROM continuumio/miniconda3:latest

LABEL software="BLRC - Phasing module"
LABEL description="Phasing programs for CLRC"
LABEL version="1.0"
LABEL LongPhase.version="1.4"
LABEL HTSLIB="1.16"
LABEL BCFTools="1.16"
LABEL maintainer="Tuan Nguyen"
LABEL maintainer.email="tuan.nguyen@agriculture.vic.gov.au"

COPY clrc_phasing.yml /
SHELL ["/bin/bash", "--login", "-c"]
RUN conda env create -f /clrc_phasing.yml && conda clean -a
RUN apt-get update && apt-get install git gcc g++ make autoconf zlib1g-dev libbz2-dev liblzma-dev bash -y
RUN git clone https://github.com/twolinin/longphase.git
WORKDIR /longphase
RUN autoreconf -i && ./configure && make -j 4
RUN cp longphase /usr/local/bin/
RUN conda activate clrc_phasing_env
ENV PATH /opt/conda/envs/clrc_phasing_env/bin:$PATH
