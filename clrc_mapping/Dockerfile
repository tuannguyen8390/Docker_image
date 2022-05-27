FROM nfcore/base:1.9

COPY clrc_mapping.yml /

SHELL ["/bin/bash", "--login", "-c"]

RUN conda env create -f /clrc_mapping.yml && conda clean -a

RUN conda activate clrc_mapping_env

ENV PATH /opt/conda/envs/clrc_mapping_env/bin:$PATH
