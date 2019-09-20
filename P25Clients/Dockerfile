FROM ubuntu:18.10
RUN mkdir /opt/dvswitch /opt/dvswitch/bin /opt/dvswitch/etc
WORKDIR /opt/dvswitch

RUN apt-get update -y && apt-get install -y git-core curl g++ make jq
RUN git clone https://github.com/g4klx/P25Clients.git
RUN cd P25Clients/P25Gateway && make clean && make && cp P25Gateway /opt/dvswitch/bin
ADD P25Gateway.ini /opt/dvswitch/etc/P25Gateway.ini
CMD /opt/dvswitch/bin/P25Gateway /opt/dvswitch/etc/P25Gateway.ini
