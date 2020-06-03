RUN systemctl start firewalld
RUN firewall-cmd --zone=public --add-masquerade --permanent
RUN firewall-cmd --zone=public --add-port=80/tcp
RUN firewall-cmd --zone=public --add-port=443/tcp
RUN firewall-cmd=443/tcp
RUN setenforce 0
RUN systemctl stop firewalld
FROM centos

RUN yum install httpd -y
RUN yum install php -y
RUN yum install /sbin/service -y

COPY root/ws2/web/  /var/www/html

EXPOSE 80

CMD /usr/sbin/httpd  -DFOREGROUND && /bin/bash
