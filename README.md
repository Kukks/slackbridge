Docker container for [slack-irc](https://github.com/ekmartin/slack-irc)
===

### Installation
```
git clone https://github.com/caktux/slackbridge
```

### Configuration

Copy `config.json.sample` to `config.json` and edit to your liking.

### Building and running

Build the docker container and run it with:

```
cd slackbridge/docker
docker build -t slack-irc-bridge .
docker run --name slack-irc-bridge --restart=always -d -t slack-irc-bridge
```

For testing use `docker build -t slack-irc-bridge . ; docker run --rm --name slack-irc-bridge -t slack-irc-bridge`

Enjoy :)
