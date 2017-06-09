FROM nginx:1.13.1-alpine

COPY nginx.conf /etc/nginx/conf.d/default.conf
RUN chown -R nginx:nginx /usr/share/nginx/html
RUN chmod -R 777 /usr/share/nginx/html
