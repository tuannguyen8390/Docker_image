FROM continuumio/miniconda3:latest
LABEL software="Remora"
LABEL version="2.0"
LABEL github_repo="https://github.com/nanoporetech/remora"

SHELL ["/bin/bash", "--login", "-c"]
RUN apt-get update && apt-get install gcc g++ bash -y
RUN pip install ont-remora

