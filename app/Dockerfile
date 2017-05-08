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

COPY src/ /src

WORKDIR /src

EXPOSE 3000 3001

CMD ["pm2-docker", "--json", "ecosystem.config.js"]