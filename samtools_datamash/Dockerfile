FROM nfcore/base:1.9

COPY samtools-datamash.yml /

SHELL ["/bin/bash", "--login", "-c"]

RUN conda env create -f /samtools-datamash.yml && conda clean -a

RUN conda activate samtools-datamash-env

ENV PATH /opt/conda/envs/samtools-datamash-env/bin:$PATH
