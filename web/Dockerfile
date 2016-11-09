FROM smich/nginx

RUN mkdir -p /etc/nginx/ssl
COPY inkinisis.conf /etc/nginx/conf.d/inkinisis.conf
COPY ik-nginx.crt /etc/nginx/ssl/ik-nginx.crt
COPY ik-nginx.key /etc/nginx/ssl/ik-nginx.key