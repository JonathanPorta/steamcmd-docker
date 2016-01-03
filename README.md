# steamcmd in a Docker container
Use this as a base container when you need a working install of steamcmd.

# Example Usage
A couple ways to use this container:

### Interactively from the cmd line
`docker run -it jonathanporta/steamcmd +login anonymous`

### To install a game or game server files into the container
```
docker run -it jonathanporta/steamcmd \
  +login anonymous \
  +force_install_dir ../srv \
  +app_update 376030 validate \
  +quit
```
