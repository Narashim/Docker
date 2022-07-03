FROM ubuntu:latest
RUN apt-get update
RUN apt-get install -y openssh-server
RUN mkdir -p /var/run/sshd
RUN mkdir -p /home/dockertest
RUN useradd -d  /home/dockertest dockertest
RUN chown dockertest /home/dockertest
RUN echo 'dockertest:P@$$w0rd' | chpasswd
RUN sed -i 's/PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config
EXPOSE 22
CMD ["/usr/sbin/sshd" , "-D"]
