FROM nginx

RUN apt-get update && apt-get install -y --no-install-recommends \
    apt-utils \
    sudo \
    vim

RUN mkdir -p /etc/nginx/ssl
COPY nginx-conf.template /etc/nginx/nginx-conf.template
COPY default-conf.development.template /etc/nginx/conf.d/default-conf.development.template
COPY default-conf.production.template /etc/nginx/conf.d/default-conf.production.template
COPY nginx.crt /etc/nginx/ssl/nginx.crt
COPY nginx.key /etc/nginx/ssl/nginx.key
