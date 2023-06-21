FROM ubuntu:20.04
ENV DEBIAN_FRONTEND=noninteractive 

RUN apt-get update && apt-get install python3.9 python3-pip libbz2-dev liblzma-dev git -y

RUN pip install pysam==0.21.0 && pip install pandas==2.0.1 && pip install numpy==1.24.3 && pip install scipy==1.10.1 && pip install matplotlib==3.7.1 

RUN git clone https://github.com/fritzsedlazeck/Spectre
WORKDIR /Spectre
RUN cp spectre.py /usr/local/bin/

ENV PATH /Spectre:$PATH

CMD ["/bin/bash"]

