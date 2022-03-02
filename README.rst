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

Most of the scripts require `jupyter-repo2docker`_, and some require `x11docker
<x11docker_script>`_ (an installer for x11docker_).  Both are included in this
repo.


Usage
-----

Download the desired scripts from the bin_ folder and make them executable (and
locatable on `PATH`).  Include `jupyter-repo2docker`_ because it is required by
the others.  


Notes
-----

containerized-firefox_ is an example GUI app with X11 and sound enabled



Other similar resources
-----------------------

* zoom_:  `mdouchement/zoom-us`_

.. _jupyter-repo2docker: bin/jupyter-repo2docker
.. _x11docker_script: bin/x11docker
.. _containerized-firefox: bin/containerized-firefox
.. _bin: bin
.. _x11docker: https://github.com/mviereck/x11docker
.. _zoom: https://zoom.us/
.. _mdouchement/zoom-us: https://github.com/mdouchement/docker-zoom-us
