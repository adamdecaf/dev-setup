FROM debian:8.0

# Upgrade and Install Packages
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y curl emacs24 git openjdk-7-jdk procps ruby2.1 ssh vim wget && \
    rm -rf /var/lib/apt/lists/*

# Add configs
ADD configs.tar /tmp/
ADD bin/install-zsh /tmp/install-zsh
RUN cd /tmp/ && \
    cd /tmp/configs/ && \
    mkdir ~/.ssh/ && \
    mv /tmp/configs/ssh.conf ~/.ssh/config && \
    mv /tmp/configs/ssh ~/.ssh/id_rsa && \
    mv /tmp/configs/ssh.pub ~/.ssh/id_rsa.pub && \
    /tmp/install-zsh && \
    mv /tmp/configs/zsh ~/.zshrc && \
    mv /tmp/configs/zsh-theme ~/.oh-my-zsh/themes/my-theme.zsh-theme

# Copy over config files
# ADD
# tar up config files, COPY over, tar xf them, rm .tar

# how does networking work?
# command line VPN?
# status of ^ in prompt?

# more packages to install? -- docker fig nmap ruby scala
# setup sbt? (w/ my configs)
# need to make a user 'adam' that is the install point?
# init script that runs when root logs in?
# better bash prompt ?
# custom .bashrc
# install zsh w/ custom config
# on leave run script to check git repos for unpushed commits
# rake script integration to deploy this out to ECS, with aws creds read in.

# generic script I can download over HTTPS to setup any machine
## $ curl https://open.ashanon.us/dev-setup.sh
## $ chmod +x dev-setup.sh
## $ ./dev-setup.sh

# Remaining Steps
# 1. Copy over ssh key to github
# 2. Set up git config
# 3. Clone down and setup emacs
# 4. Clone down projects
