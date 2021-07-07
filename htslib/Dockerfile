FROM ubuntu:latest

ENV PATH="/opt/htslib-1.12/bin:${PATH}"

COPY . /tmp

RUN apt-get update && apt-get install -y \
        build-essential \
        zlib1g-dev \
        libbz2-dev \
        liblzma-dev \
    && rm -rf /var/lib/apt/lists/* \
	&& cd /tmp/htslib-1.12 \
    && ./configure \
        --disable-libcurl \
        --prefix=/opt/htslib-1.12 \
    && make \
    && make install \
    && rm -r /tmp/htslib-1.12 \
    && apt-get purge -y --auto-remove \
        build-essential \
        zlib1g-dev \
        libbz2-dev \
        liblzma-dev
