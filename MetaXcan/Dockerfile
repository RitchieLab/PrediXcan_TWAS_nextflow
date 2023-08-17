FROM mambaorg/micromamba
WORKDIR /app

USER root
RUN apt-get update \
    && apt-get install -y --no-install-recommends git \
    && rm -rf /var/lib/apt/lists/*
USER $MAMBA_USER


RUN git clone https://github.com/hakyimlab/MetaXcan

WORKDIR MetaXcan/software

RUN micromamba install -y -n base -f conda_env.yaml && \
    micromamba clean --all --yes