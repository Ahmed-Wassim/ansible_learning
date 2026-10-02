FROM ubuntu:24.04

RUN apt-get update && \
    apt-get install -y \
    	openssh-server \
	python3 \
	sudo && \
	rm -rf /var/lib/apt/lists/*

RUN mkdir /run/sshd

RUN useradd -m -s /bin/bash ansible && \
    echo "ansible:ansible" | chpasswd && \
    usermod -aG sudo ansible


RUN echo "ansible ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/ansible

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]
