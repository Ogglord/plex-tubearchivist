# TubeArchivist Plug-In - Docker mod for plex

This mod adds [TubeArchivist Plex Plug-In](https://github.com/tubearchivist/tubearchivist-plex) (Scanner and Plug-In) to Plex, to be downloaded/updated during container start. It also sets the default API key and URL to TubeArchivist.


## Getting started

In plex docker arguments, set an environment variable `DOCKER_MODS=oggelito/plex-tubearchivist`

If adding multiple mods, enter them in an array separated by `|`, such as `DOCKER_MODS=oggelito/plex-tubearchivist|linuxserver/mods:plex-xyz`

You must also specify the ```TA_API_KEY``` and ```TA_URL``` to TubeArchivist in the docker environment variables, like below:

```yaml
services:
  plex:
    image: lscr.io/linuxserver/plex:latest
    container_name: plex
    network_mode: host
    environment:
      - DOCKER_MODS=oggelito/plex-tubearchivist
      - PUID=1000
      - PGID=1000
      - TZ=Etc/UTC
      - VERSION=docker
      - TA_API_KEY=<TubeArchivist API Key>
      - TA_URL=<URL to TubeArchivist>         # e.g. https://tube.local
    volumes:
      - ./youtube:/youtube:ro                 # access to your TA media folder
    restart: unless-stopped
```

## Credits:

 - [TubeArchivist Plex Plug-In](https://github.com/tubearchivist/tubearchivist-plex) for creating the plug-in
 - [plex-absolute-hama](https://github.com/linuxserver/docker-mods/tree/plex-absolute-hama) for inspiration
