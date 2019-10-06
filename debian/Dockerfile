FROM debian:10
LABEL maintainer "Thomas Duerr <thomduerr@gmail.com>"

RUN apt-get update && \
    apt-get install -y sudo less man vim git && \
    adduser thomd && \
    echo "thomd ALL=(root) NOPASSWD:ALL" > /etc/sudoers.d/thomd && \
    chmod 0440 /etc/sudoers.d/thomd

USER thomd
WORKDIR /home/thomd
COPY .bash_aliases .

CMD ["/bin/bash"]
