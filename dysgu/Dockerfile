FROM ubuntu:20.04
ENV DEBIAN_FRONTEND=noninteractive 
ENV PATH="/root/miniconda3/bin:${PATH}"
ARG PATH="/root/miniconda3/bin:${PATH}"

LABEL software="dysgu"
LABEL version="1.3.16"
LABEL github_repo="https://github.com/kcleal/dysgu"
LABEL maintainer="Tuan Nguyen"
LABEL maintainer.email="tuan.nguyen@agriculture.vic.gov.au"
LABEL github_repo="https://github.com/tjiangHIT/cuteSV"

RUN apt-get update && apt-get install python3.9 python3-pip libbz2-dev liblzma-dev -y

RUN pip install numpy dysgu

RUN apt-get install wget -y 

RUN wget \
    https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh \
    && mkdir /root/.conda \
    && bash Miniconda3-latest-Linux-x86_64.sh -b \
    && rm -f Miniconda3-latest-Linux-x86_64.sh 

RUN conda install -c bioconda tabix
