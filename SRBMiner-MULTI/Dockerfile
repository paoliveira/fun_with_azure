FROM clearlinux:latest

LABEL org.opencontainers.image.source="https://github.com/paoliveira/fun_with_azure"

#RUN apt -y update
#RUN apt -y install wget

RUN swupd update -y
RUN swupd bundle-add wget -y

WORKDIR /usr/miner
#https://github.com/doktor83/SRBMiner-Multi/releases/download/0.7.3/SRBMiner-Multi-0-7-3-Linux.tar.xz
RUN wget https://github.com/doktor83/SRBMiner-Multi/releases/download/0.7.3/SRBMiner-Multi-0-7-3-Linux.tar.xz && tar -xf SRBMiner-Multi-0-7-3-Linux.tar.xz && rm SRBMiner-Multi-0-7-3-Linux.tar.xz

RUN ls -al SRBMiner-Multi-0-7-3
RUN ls -al SRBMiner-Multi-0-7-3/SRBMiner-Multi
RUN ls -al /usr/miner/SRBMiner-Multi-0-7-3/SRBMiner-Multi

#SRBMiner-MULTI --algorithm randomx --api-rig-name paipo --disable-gpu --cpu-threads 4 --cpu-affinity 0xf --pool us-east.cryptonight-hub.miningpoolhub.com:17024 --wallet paipo.WORKERNAME --worker WORKERNAME --password x --tls false --nicehash false --keepalive --retry-time 10 --disable-startup-monitor --randomx-use-1gb-pages
#ENTRYPOINT ["/usr/miner/SRBMiner-Multi-0-7-3/SRBMiner-Multi", "--algorithm", "randomx", "--api-rig-name", "paipo", "--disable-gpu", "--pool", "us-east.cryptonight-hub.miningpoolhub.com:17024", "--wallet", "paipo.WORKERNAME", "--worker", "WORKERNAME", "--password", "x", "--tls", "false", "--nicehash", "false", "--keepalive", "--retry-time", "10", "--disable-startup-monitor", "--randomx-use-1gb-pages"]
ENTRYPOINT ["/usr/miner/SRBMiner-Multi-0-7-3/SRBMiner-Multi", "--help"]
