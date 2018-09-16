FROM fedora:27

RUN dnf update -y
RUN dnf install vim wget -y
RUN rpm --import https://packages.microsoft.com/keys/microsoft.asc
RUN wget -q https://packages.microsoft.com/config/fedora/27/prod.repo
RUN mv prod.repo /etc/yum.repos.d/microsoft-prod.repo
RUN chown root:root /etc/yum.repos.d/microsoft-prod.repo
RUN dnf update -y
RUN dnf install dotnet-sdk-2.1 -y

CMD ["/bin/bash"]