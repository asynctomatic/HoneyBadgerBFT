FROM python:2.7

RUN apt-get update && apt-get -y install bison flex libgmp-dev libmpc-dev

RUN wget --no-check-certificate https://crypto.stanford.edu/pbc/files/pbc-0.5.14.tar.gz
RUN tar -xvf pbc-0.5.14.tar.gz
RUN cd pbc-0.5.14 && ./configure && make && make install

RUN pip install --upgrade pip setuptools
RUN pip install --upgrade greenlet
RUN pip install PySocks
RUN pip install pycrypto
RUN pip install ecdsa
RUN pip install zfec
RUN pip install gipc
RUN pip insall coincurve

RUN git clone https://github.com/asynctomatic/charm.git
RUN cd charm && git checkout 2.7-dev && ./configure.sh && make install

RUN git clone https://github.com/asynctomatic/HoneyBadgerBFT.git
RUN cd HoneyBadgerBFT
COPY start.sh /
CMD sh /start.sh
