FROM mogtofu33/alpine-base:edge

MAINTAINER moimog33@gmail.com

# Set specific uid/gid to web server user to fix permissions issues.
#ENV LOCAL_UID= \
#    LOCAL_GID=

# Install Nginx
RUN apk add --update nginx

# Clean
RUN rm -rf /var/cache/apk/*

COPY config/nginx.conf /etc/nginx/nginx.conf

COPY scripts/run.sh /scripts/run.sh
RUN chmod +x /scripts/run.sh

EXPOSE 80
EXPOSE 443

VOLUME ["/www", "/var/log/nginx"]

ENTRYPOINT ["/bin/bash" , "/scripts/run.sh"]
