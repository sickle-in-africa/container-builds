FROM ubuntu:latest

ENV PATH="/opt/EIG-7.2.1/bin:${PATH}"

COPY . /tmp

RUN apt-get update && apt-get install -y \
        build-essential \
        libgsl-dev \
        libopenblas-dev \
        liblapacke-dev \
    && rm -rf /var/lib/apt/lists/* \
    && cd /tmp/EIG-7.2.1/src \
    && make LDLIBS="-llapacke" \
    && make install \
    && mkdir /opt/EIG-7.2.1 \
    && mv /tmp/EIG-7.2.1/bin /opt/EIG-7.2.1/bin \
    && rm -r /tmp/* \
    && apt-get purge -y --auto-remove \
        build-essential