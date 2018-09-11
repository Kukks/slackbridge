FROM node

ENV DEBIAN_FRONTEND noninteractive

# Usual update and install
RUN apt-get update && apt-get install -y supervisor

# Get slack-irc
RUN git clone https://github.com/ekmartin/slack-irc.git && \
    cd slack-irc && \
    npm install && \
    npm run build


# Add supervisor configs
ADD supervisord.conf supervisord.conf

CMD ["-n", "-c", "/supervisord.conf"]
ENTRYPOINT ["/usr/bin/supervisord"]
