=======
Dockash
=======

Programs (collectively) requiring only Docker and Bash


This repo contains bash scripts that run containerized programs.  This provides
an alternative to actually installing the programs on the host system.


Requirements
------------

The only requirements are Docker and bash.  

These scripts have been tested on Ubuntu.  On other distros, they may work
unchanged or may require modifications to some paths or shebang lines.


Installation
------------

Download the dockash_ script, save it to a location that is listed in PATH.


Usage
-----

The apps available all have names corresponding to subfolders of the src_ folder.

To make an app available, use:

```bash
dockash check-app <app name>
```

If the app isn't already installed, this will download the appropriate script
and save it in the same location as the dockash script. 

Notes
-----

containerized-firefox_ is an example GUI app with X11 and sound enabled



Other similar resources
-----------------------

* zoom_:  `mdouchement/zoom-us`_

.. _jupyter-repo2docker: bin/jupyter-repo2docker
.. _x11docker_script: bin/x11docker
.. _containerized-firefox: bin/containerized-firefox
.. _src: src
.. _x11docker: https://github.com/mviereck/x11docker
.. _zoom: https://zoom.us/
.. _mdouchement/zoom-us: https://github.com/mdouchement/docker-zoom-us
