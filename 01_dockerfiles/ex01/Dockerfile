FROM debian

EXPOSE 9987
EXPOSE 10011
EXPOSE 30033
EXPOSE 41144

RUN apt-get update -y && apt-get upgrade -y && apt-get install wget -y
RUN useradd newuser && su newuser

WORKDIR /home/newuser

RUN wget http://dl.4players.de/ts/releases/3.0.11.2/teamspeak3-server_linux-amd64-3.0.11.2.tar.gz
RUN tar -zxvf teamspeak3-server_linux-amd64-3.0.11.2.tar.gz

WORKDIR teamspeak3-server_linux-amd64

COPY createinifile.ini /home/newuser/teamspeak3-server_linux-amd64/createinifile.ini
USER newuser

ENTRYPOINT ["sh", "ts3server_minimal_runscript.sh", "inifile=createinifile.ini"]
