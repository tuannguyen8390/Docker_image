FROM nfcore/base:1.9

COPY minimap2.yml /

SHELL ["/bin/bash", "--login", "-c"]

RUN conda env create -f /minimap2.yml && conda clean -a

RUN conda activate minimap2-env

ENV PATH /opt/conda/envs/minimap2-env/bin:$PATH
