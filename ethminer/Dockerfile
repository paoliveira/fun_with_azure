FROM nvidia/cuda:11.3.0-devel-ubuntu18.04

LABEL org.opencontainers.image.source="https://github.com/paoliveira/fun_with_azure"

WORKDIR /usr/miner

RUN apt -y update
RUN apt -y install wget

#https://github.com/ethereum-mining/ethminer/releases/download/v0.19.0-alpha.0/ethminer-0.19.0-alpha.0-cuda-9-linux-x86_64.tar.gz
RUN wget https://github.com/ethereum-mining/ethminer/releases/download/v0.19.0-alpha.0/ethminer-0.19.0-alpha.0-cuda-9-linux-x86_64.tar.gz \
    && tar -xf ethminer-0.19.0-alpha.0-cuda-9-linux-x86_64.tar.gz \
    && rm ethminer-0.19.0-alpha.0-cuda-9-linux-x86_64.tar.gz

#RUN pwd
#RUN ls -al
#RUN ls -al bin

# Env setup
ENV GPU_FORCE_64BIT_PTR=0
ENV GPU_MAX_HEAP_SIZE=100
ENV GPU_USE_SYNC_OBJECTS=1
ENV GPU_MAX_ALLOC_PERCENT=100
ENV GPU_SINGLE_ALLOC_PERCENT=100

ENTRYPOINT ["/usr/miner/bin/ethminer", "-U"]
