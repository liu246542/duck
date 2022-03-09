# Version: 0.0.1
FROM aowatchsea/charm:stable
WORKDIR /root
RUN apt install -y libffi-dev
RUN pip3 install jupyterlab
RUN apt install -y python3-scipy python3-numpy
RUN pip3 install phe
EXPOSE 8888
