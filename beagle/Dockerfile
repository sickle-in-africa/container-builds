FROM ubuntu:latest

COPY . /tmp

RUN apt-get update \
    && apt-get install -y  \
        default-jdk \
    && rm -rf /var/lib/apt/lists/* \
    && mkdir /usr/java \
    && mv /tmp/*.jar /usr/java \
    && mv /tmp/* /usr/bin \
    && chmod +x /usr/bin/beagle \
    && chmod +x /usr/bin/bref3 \
    && chmod +x /usr/bin/unbref3 \
    && chmod +x /usr/bin/conform-gt
