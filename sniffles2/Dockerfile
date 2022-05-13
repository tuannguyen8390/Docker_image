FROM nfcore/base:1.9

COPY sniffles2.yml /

SHELL ["/bin/bash", "--login", "-c"]

RUN conda env create -f /sniffles2.yml && conda clean -a

RUN conda activate sniffles2-env

ENV PATH /opt/conda/envs/sniffles2-env/bin:$PATH
