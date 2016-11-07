FROM node:boron

ENV HOME /root

#VOLUME "/private/inkinisis:/src"

RUN apt-get update && apt-get install -y --no-install-recommends \
    apt-utils \
    sudo \
    vim

#RUN mkdir -p /src
COPY src/ /src

WORKDIR /src

RUN npm install -g \
    express-generator \
    # Node process manager
    pm2 \
    # A command line tool for https://github.com/locomote/node-migrate-orm2 .
    orm-migrate

RUN npm install --unsafe-perm

EXPOSE 8080

CMD ["npm", "start"]

# Create a script to do npm install and express generate
# RUN express inkinisis_app