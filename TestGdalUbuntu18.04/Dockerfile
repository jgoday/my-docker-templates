FROM ubuntu:18.04

RUN apt update
RUN apt-get install apt-transport-https vim wget -y
RUN wget -q https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb
RUN dpkg -i packages-microsoft-prod.deb
RUN apt-get update
RUN apt-get install dotnet-sdk-2.1 -y

CMD ["/bin/bash"]