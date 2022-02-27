FROM nvidia/cuda:11.1-cudnn8-devel-ubuntu18.04

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y \
      build-essential \
      wget \
      curl \
      git \	
      && rm -rf /var/lib/apt/lists/*

RUN mkdir colabfold
WORKDIR /colabfold
COPY install_colabbatch_linux.sh .
RUN /bin/bash install_colabbatch_linux.sh
COPY . .
ENTRYPOINT ["colabfold_batch/bin/colabfold_batch"]
