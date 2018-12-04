FROM centos:latest

RUN yum update -y
RUN yum install vim wget -y
RUN rpm --import https://packages.microsoft.com/keys/microsoft.asc
RUN wget -q https://packages.microsoft.com/config/centos/7/prod.repo
RUN mv prod.repo /etc/yum.repos.d/microsoft-prod.repo
RUN chown root:root /etc/yum.repos.d/microsoft-prod.repo
RUN yum update -y
RUN yum install centos-release-dotnet -y
RUN yum install rh-dotnet21-dotnet-sdk-2.1 rh-dotnet21-dotnet  -y
RUN source /opt/rh/rh-dotnet21/enable
CMD ["/bin/bash"]