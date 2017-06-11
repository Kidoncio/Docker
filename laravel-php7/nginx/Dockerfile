FROM nginx:latest
MAINTAINER Lucas Nascimento <lucas@lapou.com.br>

COPY nginx.conf /etc/nginx/conf.d/default.conf
RUN chown -R nginx:nginx /usr/share/nginx/html
RUN chmod -R 777 /usr/share/nginx/html