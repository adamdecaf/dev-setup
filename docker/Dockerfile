FROM debian:8.0

# Upgrade and Install Packages
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y curl emacs24 git openjdk-7-jdk procps ruby2.1 ssh vim w3m wget && \
    rm -rf /var/lib/apt/lists/*

# Add configs
ADD configs.tar /tmp/
RUN cd /tmp/ && \
    cd /tmp/configs/ && \
    mkdir ~/.ssh/ && \
    mv /tmp/configs/ssh.conf /root/.ssh/config && \
    mv /tmp/configs/ssh /root/.ssh/id_rsa && \
    mv /tmp/configs/ssh.pub /root/.ssh/id_rsa.pub && \
    mv /tmp/configs/git /root/.gitconfig && \
    chown root /root/.ssh/config && \
    chmod 400 /root/.ssh/config && \
    chown root /root/.ssh/id_rsa && \
    chmod 400 /root/.ssh/id_rsa && \
    chown root /root/.ssh/id_rsa.pub && \
    chmod 400 /root/.ssh/id_rsa.pub && \
    mv /tmp/configs/motd /etc/motd

# Emacs
RUN mkdir /root/bin/ && \
    mkdir -p /root/src/ && \
    cd /root/src/ && \
    rm -rf /root/.emacs.d/ && \
    git clone git@github.com:adamdecaf/emacs.d.git /root/.emacs.d/ && \
    git clone git@github.com:adamdecaf/custom-emacs-files.git /root/.emacs.d/custom/

# Projects
RUN mv /tmp/configs/bashrc /root/.bashrc && \
    mkdir -p /root/src/third-party && \
    git clone git@github.com:paulp/sbt-extras.git /root/src/third-party/sbt/ && \
    ln -s /root/src/third-party/sbt/sbt /root/bin/sbt
