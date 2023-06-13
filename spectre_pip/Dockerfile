# Use the base Python image
FROM python:3.8.5

RUN pip install pysam==0.21.0 && RUN pip install pandas==2.0.1 && RUN pip install numpy==1.24.3 && RUN pip install scipy==1.10.1 && RUN pip install matplotlib==3.7.1 

RUN git clone https://github.com/fritzsedlazeck/Spectre
WORKDIR /Spectre
RUN cp spectre.py /usr/local/bin/

CMD ["/bin/bash"]

