#### BASE IMAGE ####
FROM  --platform=linux/amd64 alpine:latest
#### METADATA ####
LABEL author="Tuan Nguyen(tuan.nguyen@agriculture.vic.gov.au)"
LABEL version="2.10.0"
LABEL software="BLAST"
LABEL description="BLAST is BLAST "
LABEL dependencies="PERL, UNZIP,...."

RUN apk add --update wget

RUN wget https://ftp.ncbi.nlm.nih.gov/blast/executables/blast+/2.10.0/ncbi-blast-2.10.0+-x64-linux.tar.gz && tar zxvpf ncbi-blast-2.10.0+-x64-linux.tar.gz && rm ncbi-blast-2.10.0+-x64-linux.tar.gz

ENV PATH=$PATH:/ncbi-blast-2.10.0+/bin
