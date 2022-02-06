#### BASE IMAGE ####
FROM ubuntu:16.04
#### METADATA ####
LABEL maintainer="Tuan Nguyen (tnguyen@agriculture.vic.gov.au)"
LABEL version="0.1"
LABEL software="FASTQC"
LABEL description="FASTQC is a quality control tool for high throughput sequence data"

#### UPDATE SOFTWARE ####
RUN apt-get update && apt-get install -y software-properties-common wget libfindbin-libs-perl software-properties-common unzip

RUN apt-get update && \
	apt-get install -y openjdk-8-jre && \
	rm -rf /var/lib/apt/lists/*

ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64/

#### INSTALLATION & ENVIRONMENT ####

RUN wget https://www.bioinformatics.babraham.ac.uk/projects/fastqc/fastqc_v0.11.9.zip -O /tmp/fastqc.zip && \
    unzip /tmp/fastqc.zip -d /opt/ && \
    rm /tmp/fastqc.zip && \
    chmod 777 /opt/FastQC/fastqc

ENV PATH="/opt/FastQC/:${PATH}"

ENTRYPOINT ["fastqc"]
