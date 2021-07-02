FROM debian:stretch-20210208-slim

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update -y &&\
    apt-get dist-upgrade -y &&\
    apt-get install -y apache2 \
        wget \
        build-essential &&\
    apt-get autoremove &&\
    apt-get clean &&\
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# +--------------------+
# HEARTBLEED
# +--------------------+

RUN wget http://snapshot.debian.org/archive/debian/20130319T033933Z/pool/main/o/openssl/libssl1.0.0_1.0.1e-2_amd64.deb -O /tmp/libssl1.0.0_1.0.1e-2_amd64.deb && \
    dpkg -i /tmp/libssl1.0.0_1.0.1e-2_amd64.deb

RUN wget http://snapshot.debian.org/archive/debian/20130319T033933Z/pool/main/o/openssl/openssl_1.0.1e-2_amd64.deb -O /tmp/openssl_1.0.1e-2_amd64.deb &&\
    dpkg -i /tmp/openssl_1.0.1e-2_amd64.deb
