FROM jupyter/datascience-notebook:ecabcb829fe0

USER root

# install required libraries

RUN cd /tmp \
  && wget http://prdownloads.sourceforge.net/ta-lib/ta-lib-0.4.0-src.tar.gz \
  && tar -xvf ta-lib-0.4.0-src.tar.gz \
  && cd ta-lib \
  && ./configure --prefix=/usr \
  && (make -j4 || make) \
  && make install \
  && rm -rf /tmp/*

RUN pip install \
  ccxt==1.53.20 \
  lightgbm==3.2.1 \
  TA-Lib==0.4.21 \
  "git+https://github.com/richmanbtc/crypto_data_fetcher.git@v0.0.12#egg=crypto_data_fetcher"

USER jovyan
