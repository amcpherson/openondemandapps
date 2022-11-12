FROM rocker/tidyverse:4.2.2

LABEL author="amcpherson"

# docker build -t amcpherson/rocker-custom:latest -t amcpherson/rocker-custom:4.2.2 .
# docker push amcpherson/rocker-custom:latest
# docker push amcpherson/rocker-custom:4.2.2

RUN apt-get update
RUN apt-get install -y git wget unzip libxt-dev
RUN apt-get install -y libbz2-dev
RUN apt-get install -y liblzma-dev
RUN apt-get install -y libglpk40
RUN apt-get install -y libhdf5-dev

USER root

