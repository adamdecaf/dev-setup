FROM adamdecaf/dev-setup-base:latest

# Emacs custom
RUN git clone git@github.com:adamdecaf/custom-emacs-files.git /root/.emacs.d/custom/ && \
    mkdir -p /root/bin/ /root/src/third-party && \
    git clone git@github.com:paulp/sbt-extras.git /root/src/third-party/sbt/ && \
    ln -s /root/src/third-party/sbt/sbt /root/bin/sbt
