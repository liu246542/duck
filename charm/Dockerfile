# Version: 0.0.1
FROM ubuntu:focal
WORKDIR /root
RUN apt update && apt install -y git vim wget python3 python3-pip m4 subversion libssl-dev flex bison
RUN wget https://gmplib.org/download/gmp/gmp-6.2.1.tar.xz
RUN tar xvf gmp-6.2.1.tar.xz
WORKDIR /root/gmp-6.2.1
RUN ./configure
RUN make && make install
WORKDIR /root
RUN wget https://crypto.stanford.edu/pbc/files/pbc-0.5.14.tar.gz
RUN tar xvf pbc-0.5.14.tar.gz
WORKDIR /root/pbc-0.5.14
RUN ./configure --prefix=$HOME/.local
RUN make && make install
WORKDIR /root
RUN wget https://github.com/JHUISI/charm/releases/download/v0.43/Charm-Crypto-0.43_Python3.tar.gz
RUN tar xvf Charm-Crypto-0.43_Python3.tar.gz
WORKDIR /root/Charm-Crypto-0.43
#RUN git clone git://github.com/JHUISI/charm.git
#WORKDIR /root/charm
#RUN sed -i 's/http/https/g' ./distribute_setup.py
#RUN sed -i "s/self.chown(tarinfo, dirpath)/self.chown(tarinfo, dirpath,'')/g" ./distribute_setup.py
RUN bash ./configure.sh
RUN make && make install
RUN ldconfig