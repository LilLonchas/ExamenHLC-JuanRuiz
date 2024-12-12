FROM ubuntu:22.04



RUN apt-get update && apt-get install -y \
    curl \
    git \
    sudo \
    openssh-server


RUN mkdir /var/run/sshd


COPY admin /usr/local/bin/admin


RUN chmod +x /usr/local/bin/admin/*.sh


RUN useradd -m usuario && echo "usuario:contraseña" | chpasswd && adduser usuario sudo

EXPOSE 22
CMD ["/usr/local/bin/admin/start.sh"]
