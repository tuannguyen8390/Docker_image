FROM nfcore/base:1.9

COPY winnowmap2.yml /

SHELL ["/bin/bash", "--login", "-c"]

RUN conda env create -f /winnowmap2.yml && conda clean -a

RUN conda activate winnowmap2-env

ENV PATH /opt/conda/envs/winnowmap2-env/bin:$PATH
