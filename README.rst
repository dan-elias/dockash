=======
Dockash
=======

Progrms (collectively) requiring only Docker and Bash


This repo contains bash scripts that run containerized programs.  This provides
an alternative to actually installing the programs on the host system and also
ensures the same version of the program and its dependencies on different
computers. 


Requirements
------------

The only requirements are Docker and bash.  

These scripts have been tested on Ubuntu.  On other distros, they may work
unchanged or may require modifications to some paths or shebang lines.

Most of the programs require `jupyter-repo2docker`_ (included in this repo)


Usage
-----

Download the desired scripts from the run_ folder and make them executable.


.. _jupyter-repo2docker: run/jupyter-repo2docker
.. _run: run
