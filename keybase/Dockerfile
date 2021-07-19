FROM ubuntu:hirsute

RUN apt-get update && apt-get install -y \
    gnupg \
    curl \
    libappindicator1 \
    fuse \
    sudo \
    zip \
    unzip

COPY keybase.zip /usr/bin/keybase.zip
RUN cd /usr/bin && unzip keybase.zip

RUN groupadd -g 1000 keybase \
    && useradd --create-home -d /home/keybase -g keybase -u 1000 keybase
RUN echo "keybase ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers
USER keybase
ENV HOME /home/keybase

WORKDIR /home/keybase

RUN mkdir $HOME/.config

#ENTRYPOINT ["keybase"]
