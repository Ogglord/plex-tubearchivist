# TubeArchivist Agent and Scanner - Docker mod for plex

This mod adds [TubeArchivist Plex Plug-In](https://github.com/tubearchivist/tubearchivist-plex) to Plex, to be downloaded/updated during container start.

In plex docker arguments, set an environment variable `DOCKER_MODS=linuxserver/mods:plex-tubearchivist`

If adding multiple mods, enter them in an array separated by `|`, such as `DOCKER_MODS=linuxserver/mods:plex-tubearchivist|linuxserver/mods:plex-somemod`
