FROM ubuntu:latest
ARG DEBIAN_FRONTEND=noninteractive
RUN apt update && apt install -y  openssh-server sudo iproute2 net-tools curl apache2
RUN useradd -rm -d /home/ubuntu -s /bin/bash -g root -G sudo -u 1000 test
RUN  echo 'test:test' | chpasswd
RUN service ssh start
RUN service apache2 start
EXPOSE 22 80
CMD ["/usr/sbin/sshd","-D"]
CMD ["apachectl", "-D", "FOREGROUND"]
RUN /bin/bash
