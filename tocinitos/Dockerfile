FROM debian:stretch

RUN echo  "deb http://deb.debian.org/debian stretch main" > /etc/apt/sources.list
RUN apt-get update && apt install -y bind9 dnsutils tcpdump && apt-get clean

ADD db.* /etc/bind/
ADD named.conf.local /etc/bind/

EXPOSE 53/udp

ADD load /load

ENTRYPOINT ["/load"]

