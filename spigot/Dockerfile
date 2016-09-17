FROM alpine:3.4
MAINTAINER Rayson Zhu <vfreex+spigot@gmail.com>

EXPOSE 25565
WORKDIR /opt/spigot/data
CMD ["java", "-Dcom.mojang.eula.agree=true", "-jar", "/opt/spigot/lib/spigot-1.9.4-R0.1.jar"]

RUN apk --no-cache add ca-certificates wget openjdk8-jre-base && \
    adduser -D spigot && \
    mkdir -p /opt/spigot/lib && \
    mkdir -p /opt/spigot/data && \
    wget -O /opt/spigot/lib/spigot-1.9.4-R0.1.jar https://www.getbukkit.org/files/spigot-1.9.4-R0.1-SNAPSHOT-latest.jar && \
    chown -R spigot: /opt/spigot && \
    apk del ca-certificates wget

