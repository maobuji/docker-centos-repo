FROM docker pull centos:centos7.3.1611
USER root
WORKDIR /opt/
COPY ../fileserver ./fileserver

WORKDIR /opt/fileserver

RUN yum install -y --downloadonly --downloaddir=/opt/fileserver/centos-repo createrepo
RUN yum install -y createrepo

RUN createrepo -d /opt/fileserver/centos-repo

RUN chmod 775 /opt/fileserver/startHttp.sh
ENTRYPOINT ["/opt/fileserver/startHttp.sh"]





