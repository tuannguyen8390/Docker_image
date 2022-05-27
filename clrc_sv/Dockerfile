FROM nfcore/base:1.9

COPY clrc_sv.yml /

SHELL ["/bin/bash", "--login", "-c"]

RUN conda env create -f /clrc_sv.yml && conda clean -a

RUN conda activate clrc_sv_env

ENV PATH /opt/conda/envs/clrc_sv_env/bin:$PATH
