FROM smich/node

COPY src/ /src

WORKDIR /src

RUN npm install --unsafe-perm

EXPOSE 3000

CMD ["pm2-docker", "--json", "process.yml"]