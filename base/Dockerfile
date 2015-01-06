FROM debian:8.0

# Upgrade and Install Packages
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y emacs24 git openjdk-7-jdk procps ruby2.1 ssh vim wget && \
    rm -rf /var/lib/apt/lists/*

# Add configs
RUN mkdir ~/bin/ ~/.ssh/ && \
    mv configs/ssh.conf /root/.ssh/config && \
    chown root /root/.ssh/config && \
    chmod 400 /root/.ssh/config && \

    mv configs/ssh /root/.ssh/id_rsa && \
    chown root /root/.ssh/id_rsa && \
    chmod 400 /root/.ssh/id_rsa && \\

    mv configs/ssh.pub /root/.ssh/id_rsa.pub && \
    chown root /root/.ssh/id_rsa.pub && \
    chmod 400 /root/.ssh/id_rsa.pub && \

    mv configs/git /root/.gitconfig && \
    mv /tmp/configs/bashrc /root/.bashrc && \
    mv /tmp/configs/motd /etc/motd

# Emacs
RUN rm -rf /root/.emacs.d/ && \
    git clone git@github.com:adamdecaf/emacs.d.git /root/.emacs.d/
