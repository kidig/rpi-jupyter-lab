FROM kidig/rpi-jupyter-lab:latest
MAINTAINER Dmitry Gerasimenko <kiddima@gmail.com>


RUN apt-get update && apt-get install -y libhdf5-dev liblapack-dev gfortran libfreetype6-dev libpng-dev

COPY requirements.txt .
RUN pip3 install -vv -r requirements.txt
