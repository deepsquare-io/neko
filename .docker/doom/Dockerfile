ARG BASE_IMAGE=m1k1o/neko:base
FROM $BASE_IMAGE

#
# install doom
RUN set -eux; apt-get update; \
    apt-get install -y openbox chocolate-doom doom-wad-shareware prboom-plus freedoom; \
    apt-get clean -y; \
    rm -rf /var/lib/apt/lists/* /var/cache/apt/*

RUN mkdir -p /home/neko/.local/share/chocolate-doom

COPY chocolate-doom.cfg /home/neko/.local/share/chocolate-doom/chocolate-doom.cfg
COPY default.cfg /home/neko/.local/share/chocolate-doom/default.cfg

#
# copy configuation files
COPY supervisord.conf /etc/neko/supervisord/doom.conf
COPY openbox.xml /etc/neko/openbox.xml
