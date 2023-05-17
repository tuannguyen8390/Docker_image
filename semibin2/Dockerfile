FROM mambaorg/micromamba

# Install micromamba and create SemiBin2 environment
RUN micromamba create -n SemiBin2 -c conda-forge -c bioconda python=3.8 semibin

ENV PATH ./root/micromamba/envs/SemiBin2/bin/:$PATH
