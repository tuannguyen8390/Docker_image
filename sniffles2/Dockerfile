FROM ubuntu:20.04

LABEL software="CLRC - Sniffles2 module"
LABEL description="Sniffles2 module"
LABEL version="2.0.6"
LABEL maintainer="Tuan Nguyen"
LABEL maintainer.email="tuan.nguyen@agriculture.vic.gov.au"

RUN apt-get update && apt-get install software-properties-common -y && add-apt-repository ppa:deadsnakes/ppa && apt-get install python3.9 python3-pip libbz2-dev liblzma-dev -y

RUN pip install sniffles
