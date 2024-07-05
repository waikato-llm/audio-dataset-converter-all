ARG DOCKER_REGISTRY=public.aml-repo.cms.waikato.ac.nz:443/
FROM ${DOCKER_REGISTRY}ubuntu:22.04

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
       git-core \
       wget \
       python3 \
       python3-dev \
       python3-venv \
       python3-pip \
       python3-pandas \
       python3-chardet \
       build-essential \
       libsndfile1 \
       libsndfile1-dev \
       libglib2.0-0 \
       libsm6 \
       libxrender-dev \
       libxext6 \
       libgl1-mesa-glx \
       libpq-dev && \
    rm -rf /var/lib/apt/lists/*

RUN pip3 --no-cache-dir install \
        audio-dataset-converter-all==0.0.1

COPY bash.bashrc /etc/bash.bashrc

WORKDIR /workspace
