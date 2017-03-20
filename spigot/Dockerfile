FROM alpine:3.5
LABEL maintainer Yuxiang Zhu <vfreex+container@gmail.com>

EXPOSE 25565
ARG SPIGOT_VERSION=1.11.2

RUN set -x && cd \
    && apk add --update su-exec openjdk8-jre-base \
    && apk add --virtual .build-deps openssl shadow \
    && mkdir -p /opt/spigot/lib \
    && wget -O /opt/spigot/lib/spigot.jar "https://cdn.getbukkit.org/spigot/spigot-$SPIGOT_VERSION.jar" \
    && mkdir -p /opt/spigot/data \
    && groupadd -r spigot && useradd -g spigot -r spigot \
    && chown spigot: /opt/spigot/data \
    && apk del .build-deps \
    && rm -rf /var/cache/apk/*

WORKDIR /opt/spigot/data
CMD ["/sbin/su-exec", "spigot", "java", "-Dcom.mojang.eula.agree=true", "-jar", "/opt/spigot/lib/spigot.jar"]
