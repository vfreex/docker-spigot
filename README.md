# docker-spigot

This repo contains Dockerfile and Docker compose file to create Docker images
and/or containers for [Spigot].

[Spigot] is the most widely-used modded Minecraft server software in the world.

## Run Spigot in Docker

Suppose you have Docker Engine and Docker Compose installed.
If not, see <https://docs.docker.com/engine/installation/> and <https://docs.docker.com/compose/install/>.

``` sh
# Clone from Github
git clone https://github.com/vfreex/docker-spigot.git
cd docker-spigot

# Run Spigot in the background
docker-compose up -d

# By default, the Docker compose file will map TCP port 25565 to the container
# All Spigot configuration and data files will go towards `data/spigot`

# Access to Spigot's command line
docker attach `docker-compose ps -q`

# Detach from shell by pressing CTRL+P, CTRL+Q

```

[Spigot]: https://www.spigotmc.org/wiki/about-spigot/
