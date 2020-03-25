FROM continuumio/miniconda:4.5.11

WORKDIR /hicer-nf

COPY environment.yml /hicer-nf/environment.yml


RUN apt-get update \
    && apt-get install -y procps \
    && apt-get clean -y \
    && conda config --add channels defaults \
    && conda config --add channels bioconda \
    && conda config --add channels conda-forge \
    && conda env create --name hicer-nf -f environment.yml \
    && rm -rf /opt/conda/pkgs/*

ENV PATH /opt/conda/envs/hicer-nf/bin:$PATH
