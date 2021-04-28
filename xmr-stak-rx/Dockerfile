FROM ubuntu:latest

LABEL org.opencontainers.image.source="https://github.com/paoliveira/fun_with_azure"

RUN apt-get -y update

WORKDIR /usr/miner
#ADD xmr-stak-rx-linux-1.0.5-cpu.tar.xz /usr/xmr-stak-rx/
#COPY config.txt /usr/xmr-stak-rx/xmr-stak-rx-linux-1.0.5-cpu/
#COPY cpu.txt /usr/xmr-stak-rx/xmr-stak-rx-linux-1.0.5-cpu/
#COPY pools.txt /usr/xmr-stak-rx/xmr-stak-rx-linux-1.0.5-cpu/

#https://github.com/fireice-uk/xmr-stak/releases/download/1.0.5-rx/xmr-stak-rx-linux-1.0.5-cpu.tar.xz
RUN wget https://github.com/fireice-uk/xmr-stak/releases/download/1.0.5-rx/xmr-stak-rx-linux-1.0.5-cpu.tar.xz && tar zxvpf xmr-stak-rx-linux-1.0.5-cpu.tar.xz && rm xmr-stak-rx-linux-1.0.5-cpu.tar.xz

#ENTRYPOINT ["/usr/miner/xmr-stak-rx-linux-1.0.5-cpu/xmr-stak-rx", "--url", "us-east.cryptonight-hub.miningpoolhub.com:20580", "--user", "paipo.WORKERNAME", "--pass", "x", "--currency", "monero"]
ENTRYPOINT ["/usr/miner/xmr-stak-rx-linux-1.0.5-cpu/xmr-stak-rx", "--help"]
