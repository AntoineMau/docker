FROM debian
RUN apt-get update -y && apt-get upgrade -y

RUN useradd teamspeak
WORKDIR /home/teamspeak
RUN wget http://dl.4players.de/ts/releases/3.0.11.2/teamspeak3-server_linux-amd64-3.0.11.2.tar.gz
RUN tar -zxvf teamspeak3-server_linux-amd64-3.0.11.2.tar.gz
RUN rm teamspeak3-server_linux-amd64-3.0.11.2.tar.gz
WORKDIR /home/teamspeak/teamspeak3-server_linux-amd64
RUN ./ts3server_minimal_runscript.sh createinifile=1
