FROM nginxinc/nginx-unprivileged:1-alpine

COPY ./nginx.conf /etc/nginx/conf.d/default.conf
COPY ./uwsgi_params /etc/nginx/uwsgi_params
# Temporarily switch to root user to give 755 permissions to static folder
USER root
RUN mkdir -p /vol/static
RUN chmod 755 /vol/static
# Switch back to nginx user
USER nginx