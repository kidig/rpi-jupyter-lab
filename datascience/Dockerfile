FROM kidig/rpi-jupyter-lab:latest
MAINTAINER Dmitry Gerasimenko <kiddima@gmail.com>


RUN apt-get update && apt-get install -y libhdf5-dev liblapack-dev gfortran

COPY requirements.txt .
RUN pip3 install -r requirements.txt
