FROM clearlinux:latest

LABEL org.opencontainers.image.source="https://github.com/paoliveira/fun_with_azure"

#RUN apt -y update
#RUN apt -y install wget

RUN swupd update -y
RUN swupd bundle-add wget -y

WORKDIR /usr/miner
#https://github.com/doktor83/SRBMiner-Multi/releases/download/0.7.3/SRBMiner-Multi-0-7-3-Linux.tar.xz
RUN wget https://github.com/doktor83/SRBMiner-Multi/releases/download/0.7.3/SRBMiner-Multi-0-7-3-Linux.tar.xz && tar -xf SRBMiner-Multi-0-7-3-Linux.tar.xz && rm SRBMiner-Multi-0-7-3-Linux.tar.xz

#SRBMiner-MULTI --algorithm randomx --api-rig-name paipo --disable-gpu --cpu-threads 4 --cpu-affinity 0xf --pool us-east.cryptonight-hub.miningpoolhub.com:20580 --wallet paipo.WORKERNAME --worker WORKERNAME --password x --tls false --nicehash false --keepalive --retry-time 10 --disable-startup-monitor --randomx-use-1gb-pages
#SRBMiner-MULTI --algorithm randomx --disable-gpu --cpu-threads 4 --cpu-affinity 0xf --pool us-east.cryptonight-hub.miningpoolhub.com:20580 --wallet paipo.WORKERNAME --worker WORKERNAME --password x --tls false --nicehash false --keepalive --retry-time 10 --disable-startup-monitor --randomx-use-1gb-pages
#SRBMiner-MULTI --algorithm randomx --disable-gpu --pool us-east.cryptonight-hub.miningpoolhub.com:20580 --wallet paipo.WORKERNAME --worker WORKERNAME --password x --tls false --nicehash false --keepalive --retry-time 10 --disable-startup-monitor
#ENTRYPOINT ["/usr/miner/SRBMiner-Multi-0-7-3/SRBMiner-MULTI", "--algorithm", "randomx", "--disable-gpu", "--pool", "us-east.cryptonight-hub.miningpoolhub.com:20580", "--wallet", "paipo.docker", "--password", "x", "--tls", "false", "--nicehash", "false", "--keepalive", "--retry-time", "10", "--disable-startup-monitor"]
ENTRYPOINT ["/usr/miner/SRBMiner-Multi-0-7-3/SRBMiner-MULTI", "--help"]
