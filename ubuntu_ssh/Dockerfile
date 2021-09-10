FROM ubuntu:latest
RUN apt update && apt install -y  openssh-server sudo iproute2 net-tools curl 
RUN useradd -rm -d /home/ubuntu -s /bin/bash -g root -G sudo -u 1000 test
RUN  echo 'test:test' | chpasswd
RUN service ssh start
COPY ./authorized_keys /root/.ssh/
RUN /bin/bash
EXPOSE 22 
ENTRYPOINT ["/usr/sbin/sshd", "-D"]

