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

Most of the programs require `jupyter-repo2docker`_ (included in this repo)


Usage
-----

Download the desired scripts from the run_ folder and make them executable (and
locatable on `PATH`).  Include `jupyter-repo2docker`_ because it is required by
the others.  

Also, currently, `jupyter-repo2docker`_ requires write access to the docker
socket.  An insecure but quick hack to achieve this is:

..code:: bash

    sudo chmod 666 /var/run/docker.sock


.. _jupyter-repo2docker: run/jupyter-repo2docker
.. _run: run
