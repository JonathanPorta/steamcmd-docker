# steamcmd in a Docker container [![Docker Repository on Quay](https://quay.io/repository/jonathanporta/steamcmd/status "Docker Repository on Quay")](https://quay.io/repository/jonathanporta/steamcmd)
Use this as a base container when you need a working install of steamcmd.

# Example Usage
A couple ways to use this container:

### Interactively from the cmd line
`docker run -it jonathanporta/steamcmd +login anonymous`

### To install a game or game server files into the container
```
docker run -it jonathanporta/steamcmd \
  +login anonymous \
  +force_install_dir /srv \
  +app_update 376030 validate \
  +quit
```

### Use this as a base image for building a server container
```
# Dockerfile
FROM jonathanporta/steamcmd

# Install Ark server files
RUN ./steamcmd.sh +login anonymous \
  +force_install_dir /srv \
  +app_update 376030 validate \
  +quit

# Set the server executable as the entrypoint
ENTRYPOINT ["/srv/ShooterGame/Binaries/Linux/ShooterGameServer"]

...
```
