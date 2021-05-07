FROM nvidia/cuda:11.3.0-devel-ubuntu18.04

LABEL org.opencontainers.image.source="https://github.com/paoliveira/fun_with_azure"

WORKDIR /usr/miner

RUN apt -y update
RUN apt -y install unzip

#https://github.com/ethereum-mining/ethminer/releases/download/v0.19.0-alpha.0/ethminer-0.19.0-alpha.0-cuda10.0-windows-amd64.zip
RUN wget https://github.com/ethereum-mining/ethminer/releases/download/v0.19.0-alpha.0/ethminer-0.19.0-alpha.0-cuda10.0-windows-amd64.zip \
    && unzip ethminer-0.19.0-alpha.0-cuda10.0-windows-amd64.zip \
    && rm ethminer-0.19.0-alpha.0-cuda10.0-windows-amd64.zip

RUN ls -al
RUN ls -al ethminer-0.19.0-alpha.0-cuda10.0-windows-amd64

# Env setup
ENV GPU_FORCE_64BIT_PTR=0
ENV GPU_MAX_HEAP_SIZE=100
ENV GPU_USE_SYNC_OBJECTS=1
ENV GPU_MAX_ALLOC_PERCENT=100
ENV GPU_SINGLE_ALLOC_PERCENT=100

ENTRYPOINT ["/usr/miner/ethminer", "-U"]
