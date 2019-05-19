FROM fedora:28

RUN dnf -y install 'dnf-command(copr)' && \
    dnf -y copr enable @cekit/cekit && \
    dnf -y install python3-cekit && \
    #create jdg user
    useradd -ms /bin/bash jdg && \
    usermod jdg -a -G wheel && \
    echo '%wheel ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers && \
    # cleanup
    dnf clean all

USER jdg
WORKDIR /home/jdg
ENV LANG en_US.UTF-8

COPY config /home/jdg/.cekit/
