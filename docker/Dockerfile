FROM ubuntu:xenial

ENV DEBIAN_FRONTEND noninteractive

# Usual update / upgrade
RUN apt-get update && apt-get upgrade -y && apt-get dist-upgrade -y

# Install requirements
RUN apt-get install -y curl supervisor git make gcc g++ apt-utils libicu-dev

# Install nodejs
RUN curl -sL https://deb.nodesource.com/setup_6.x | bash -
RUN apt-get install --fix-missing -y nodejs

# Get slack-irc
RUN git clone https://github.com/markus456/slack-irc.git && \
    cd slack-irc && \
    npm install && \
    npm run build

# Add configurations
ADD config.json /slack-irc/config.json

# Add supervisor configs
ADD supervisord.conf supervisord.conf

CMD ["-n", "-c", "/supervisord.conf"]
ENTRYPOINT ["/usr/bin/supervisord"]
