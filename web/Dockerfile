FROM smich/nginx

RUN mkdir -p /etc/nginx/ssl
COPY inkinisis.template /etc/nginx/conf.d/inkinisis.template
COPY ik-nginx.crt /etc/nginx/ssl/ik-nginx.crt
COPY ik-nginx.key /etc/nginx/ssl/ik-nginx.key