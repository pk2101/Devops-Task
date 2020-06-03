FROM centos
RUN yum install curl -y
RUN yum install coreutils 
RUN yum install java -y
RUN yum install git -y

RUN curl curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl

RUN chmod +x kubectl
RUN cp kubectl /usr/bin/
RUN yum install sudo -y
COPY ca.crt /root/
COPY client.crt /root/
COPY client.key /root/

RUN mkdir .kube
COPY config /root/.kube/

RUN yum install openssh-server -y
RUN shh-keygen -A
CMD /usr/sbin/sshd  -DFOREGROUND && /bin/bash 