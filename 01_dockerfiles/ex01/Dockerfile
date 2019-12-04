FROM debian

RUN adduser --disabled-password --gecos "" teamspeak
RUN mkdir /opt/teamspeak
RUN chown teamspeak:teamspeak /opt/teamspeak/
RUN chmod 0770 /opt/teamspeak/
RUN apt-get update
RUN apt-get install -y bzip2 wget
RUN wget https://files.teamspeak-services.com/releases/server/3.9.1/teamspeak3-server_linux_amd64-3.9.1.tar.bz2
RUN tar xvf teamspeak3-server_linux_amd64-3.9.1.tar.bz2
RUN mv teamspeak3-server_linux_amd64/* /opt/teamspeak/
RUN rm -rf ~/teamspeak3-server_linux_amd64*

EXPOSE 9987/udp 
EXPOSE 30033
EXPOSE 10011
ENV TS3SERVER_LICENSE=accept
WORKDIR /opt/teamspeak
ENTRYPOINT sh ts3server_minimal_runscript.sh