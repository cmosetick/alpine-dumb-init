FROM node:6.10-alpine
MAINTAINER Chris Mosetick <cmosetick@gmail.com>

# switch to Alpine 3.5 repos, so we can simply 'apk add dumb-init'
COPY repositories /etc/apk/repositories

RUN \
echo -e 'http://dl-cdn.alpinelinux.org/alpine/edge/main\nhttp://dl-cdn.alpinelinux.org/alpine/edge/community\nhttp://dl-cdn.alpinelinux.org/alpine/edge/testing' >> /etc/apk/repositories && \
apk --no-cache --update add yarn dumb-init && \
rm -rf /var/cache/apk* /tmp && \
mkdir /tmp && \
chmod 777 /tmp

ENTRYPOINT ["/usr/bin/dumb-init","--"]
CMD ["/usr/local/bin/npm","start"]
