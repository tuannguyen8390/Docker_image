FROM continuumio/miniconda3:4.12.0

LABEL software="CLRC - QC module"
LABEL description="Toolkit for processing sequences in FASTA/Q formats"
LABEL version="1.0"
LABEL seqtk.version="1.3"
LABEL ropebwt2.version="r187"
LABEL nanofilt.version="2.8.0"
LABEL fmlrc2.version="0.1.7"
LABEL nanoplot="1.40.2"
LABEL maintainer="Tuan Nguyen"
LABEL maintainer.email="tuan.nguyen@agriculture.vic.gov.au"

COPY clrc_qc.yml /

SHELL ["/bin/bash", "--login", "-c"]

RUN conda env create -f /clrc_qc.yml && conda clean -a

RUN conda activate clrc_qc-env

ENV PATH /opt/conda/envs/clrc_qc-env/bin:$PATH