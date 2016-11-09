FROM smich/node

COPY src/ /src

WORKDIR /src

RUN npm install --unsafe-perm

EXPOSE 3000

CMD ["npm", "start"]

# Create a script to do npm install and express generate
# RUN express inkinisis_app