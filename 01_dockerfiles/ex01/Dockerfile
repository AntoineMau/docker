FROM debian
RUN apt-get update -y && apt-get upgrade -y \
	apt-get install wget -y \
	apt-get install bzip2 -y

EXPOSE 9987/udp
EXPOSE 30033
EXPOSE 10011
EXPOSE 41144

RUN useradd teamspeak
USER teamspeak
WORKDIR /home/teamspeak
RUN wget https://files.teamspeak-services.com/releases/server/3.6.1/teamspeak3-server_linux_amd64-3.6.1.tar.bz2 \
	tar -zxvf teamspeak3-server_linux_amd64-3.6.1.tar.bz2 \
	rm teamspeak3-server_linux_amd64-3.6.1.tar.bz2
WORKDIR /home/teamspeak/teamspeak3-server_linux-amd64
RUN ./ts3server_minimal_runscript.sh createinifile=1
COPY /home/teamspeak/teamspeak3-server_linux-amd64/ts3server.ini ts3server.ini
RUN ./ts3serveur_startscript.sh start
ENTRYPOINT ["sh","ts3serveur_startscript.sh"]