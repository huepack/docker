FROM ubuntu:latest
ARG DEBIAN_FRONTEND=noninteractive
RUN apt update && apt install -y  openssh-server sudo iproute2 net-tools curl apache2
RUN useradd -rm -d /home/ubuntu -s /bin/bash -g root -G sudo -u 1000 test
RUN  echo 'test:test' | chpasswd
RUN systemctl enable --now ssh
RUN systemctl enable --now apache2 
RUN /bin/bash
EXPOSE 22 80
CMD ["/usr/sbin/sshd","-D"]
CMD ["apachectl", "-D", "FOREGROUND"]

