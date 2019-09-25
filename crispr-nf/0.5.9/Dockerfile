FROM continuumio/miniconda:4.5.11

WORKDIR /crispr-nf

COPY environment.yml /crispr-nf/environment.yml

RUN apt-get update && apt-get install -y procps && apt-get clean -y
RUN conda config --add channels bioconda \
    && conda env create --name crispr-nf -f environment.yml \
    && rm -rf /opt/conda/pkgs/*

ENV PATH /opt/conda/envs/crispr-nf/bin:$PATH
