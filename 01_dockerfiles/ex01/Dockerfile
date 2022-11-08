FROM debian

MAINTAINER niko gardziella <gardziella@gmail.com>

EXPOSE 9987/udp 10011 30033

ENV TS3SERVER_LICENSE=accept

RUN apt-get update && apt-get upgrade -y && apt-get install -y bzip2 wget && \
wget https://files.teamspeak-services.com/releases/server/3.13.3/teamspeak3-server_linux_amd64-3.13.3.tar.bz2 && \
tar -xvf teamspeak3-server_linux_amd64-3.13.3.tar.bz2


RUN touch /teamspeak3-server_linux_amd64/.ts3server_license_accepted
RUN echo "license_accepted=1" > /teamspeak3-server_linux_amd64/.ts3server_license_accepted 

ENTRYPOINT sh /teamspeak3-server_linux_amd64/ts3server_minimal_runscript.sh

#to build: docker build -t myteamspeak .

#to run: docker run -p 9987:9987/udp -p 10011:10011 -p 30033:30033 -e TS3SERVER_LICENSE=accept myteamspeak