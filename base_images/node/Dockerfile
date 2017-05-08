FROM node:boron

ENV HOME /root

RUN apt-get update && apt-get install -y --no-install-recommends \
    apt-utils \
    sudo \
    vim

RUN npm install -g \
    express-generator \
    # Node process manager
    pm2

# Daemonize pm to make sure it restarts after a sudden crash. An executable is
# created under /etc/init.d
RUN pm2 startup