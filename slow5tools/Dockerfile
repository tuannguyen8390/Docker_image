FROM ubuntu:18.04

LABEL software="CLRC - Slow5 module"
LABEL description="Slow5 module"
LABEL version="1.0"
LABEL version="0.5"
LABEL maintainer="Tuan Nguyen"
LABEL maintainer.email="tuan.nguyen@agriculture.vic.gov.au"

WORKDIR /
RUN apt-get update && apt-get install libhdf5-dev zlib1g-dev libzstd1-dev git wget tar gcc g++ make autoconf bash  -y
RUN git clone --recursive https://github.com/hasindu2008/slow5tools
WORKDIR /slow5tools
RUN autoreconf && ./configure && make zstd=1 && zstd=1 make test
CMD ./slow5tools