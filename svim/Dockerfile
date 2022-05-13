FROM continuumio/anaconda3

COPY svim.yml /

SHELL ["/bin/bash", "--login", "-c"]

RUN conda env create -f /svim.yml && conda clean -a

RUN conda activate svim-env

ENV PATH /opt/conda/envs/svim-env/bin:$PATH
