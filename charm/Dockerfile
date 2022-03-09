# Version: 0.0.1
FROM amd64/debian:buster
WORKDIR /root
RUN apt update && apt install -y git vim wget python3 python3-pip m4 subversion libssl-dev flex bison libgmp-dev
RUN wget https://crypto.stanford.edu/pbc/files/pbc-0.5.14.tar.gz
RUN tar xvf pbc-0.5.14.tar.gz
WORKDIR /root/pbc-0.5.14
RUN ./configure LDFLAGS="-lgmp"
RUN make && make install
RUN ldconfig
WORKDIR /root
RUN git clone git://github.com/JHUISI/charm.git
WORKDIR /root/charm
RUN bash ./configure.sh
RUN make && make install
RUN ldconfig
RUN apt autoclean