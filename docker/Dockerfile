FROM debian:8.0

# Upgrade and Install Packages
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y curl emacs24 git openjdk-7-jdk procps ruby2.1 ssh vim wget && \
    rm -rf /var/lib/apt/lists/*

# Add configs
ADD configs.tar /tmp/
RUN cd /tmp/ && \
    cd /tmp/configs/ && \
    mkdir ~/.ssh/ && \
    mv /tmp/configs/ssh.conf ~/.ssh/config && \
    mv /tmp/configs/ssh ~/.ssh/id_rsa && \
    mv /tmp/configs/ssh.pub ~/.ssh/id_rsa.pub && \
    mv /tmp/configs/git ~/.gitconfig

# TODO
# 1. Copy over ssh key to github
# 2. Clone down and setup emacs
# 3. Clone down projects
# 4. setup sbt? (w/ my configs)
# 5. rake script integration to deploy this out to ECS, with aws creds read in.
# 6. need to make a user 'adam' that is the install point?

# Networking
## how does networking work?
### command line VPN? (with status of ^ in prompt?)

# generic script I can download over HTTPS to setup any machine
## $ curl https://open.ashanon.us/dev-setup.sh
## $ chmod +x dev-setup.sh
## $ ./dev-setup.sh
