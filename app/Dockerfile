FROM smich/ik_node

COPY src/ /src

WORKDIR /src

RUN npm install --unsafe-perm

EXPOSE 8080

CMD ["npm", "start"]

# Create a script to do npm install and express generate
# RUN express inkinisis_app