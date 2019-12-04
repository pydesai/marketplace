# Node-RED Docker

[![Greenkeeper badge](https://badges.greenkeeper.io/node-red/node-red-docker.svg)](https://greenkeeper.io/)
[![Build Status](https://travis-ci.org/node-red/node-red-docker.svg?branch=master)](https://travis-ci.org/node-red/node-red-docker)
[![DockerHub Pull](https://img.shields.io/docker/pulls/nodered/node-red.svg)](https://hub.docker.com/r/nodered/node-red/)
[![DockerHub Stars](https://img.shields.io/docker/stars/nodered/node-red.svg?maxAge=2592000)](https://hub.docker.com/r/nodered/node-red/)

This project describes some of the many ways Node-RED can be run under Docker and has support for multiple architectures (amd64, arm32v6, arm32v7, arm64v8, i386 and s390x).
Some basic familiarity with Docker and the [Docker Command Line](https://docs.docker.com/engine/reference/commandline/cli/) is assumed.

As of Node-RED 1.0 this project provides the build for the `nodered/node-red` container on [Docker Hub](https://hub.docker.com/r/nodered/node-red/). Note: the Docker Hub name has changed to `nodered/node-red`.

Previous 0.20.x versions are still available at https://hub.docker.com/r/nodered/node-red-docker.

## Quick Start
To run in Docker in its simplest form just run:

        docker run -it -p 1880:1880 --name mynodered nodered/node-red

Let's dissect that command:

        docker run              - run this container, initially building locally if necessary
        -it                     - attach a terminal session so we can see what is going on
        -p 1880:1880            - connect local port 1880 to the exposed internal port 1880
        --name mynodered        - give this machine a friendly local name
        nodered/node-red        - the image to base it on - currently Node-RED v1.0.3


Running that command should give a terminal window with a running instance of Node-RED.

        Welcome to Node-RED
        ===================

        03 Oct 12:57:10 - [info] Node-RED version: v1.0.3
        03 Oct 12:57:10 - [info] Node.js  version: v10.16.3
        03 Oct 12:57:10 - [info] Linux 4.9.184-linuxkit x64 LE
        03 Oct 12:57:11 - [info] Loading palette nodes
        03 Oct 12:57:16 - [info] Settings file  : /data/settings.js
        03 Oct 12:57:16 - [info] Context store  : 'default' [module=memory]
        03 Oct 12:57:16 - [info] User directory : /data
        03 Oct 12:57:16 - [warn] Projects disabled : editorTheme.projects.enabled=false
        03 Oct 12:57:16 - [info] Flows file     : /data/flows.json
        03 Oct 12:57:16 - [info] Creating new flow file
        03 Oct 12:57:17 - [warn]

        ---------------------------------------------------------------------
        Your flow credentials file is encrypted using a system-generated key.

        If the system-generated key is lost for any reason, your credentials
        file will not be recoverable, you will have to delete it and re-enter
        your credentials.

        You should set your own key using the 'credentialSecret' option in
        your settings file. Node-RED will then re-encrypt your credentials
        file using your chosen key the next time you deploy a change.
        ---------------------------------------------------------------------

        03 Oct 12:57:17 - [info] Starting flows
        03 Oct 12:57:17 - [info] Started flows
        03 Oct 12:57:17 - [info] Server now running at http://127.0.0.1:1880/

        [...]

You can then browse to `http://{host-ip}:1880` to get the familiar Node-RED desktop.


The advantage of doing this is that by giving it a name (mynodered) we can manipulate it
more easily, and by fixing the host port we know we are on familiar ground.
Of course this does mean we can only run one instance at a time... but one step at a time folks...

If we are happy with what we see, we can detach the terminal with `Ctrl-p` `Ctrl-q` - the
container will keep running in the background.

To reattach to the terminal (to see logging) run:

        $ docker attach mynodered

If you need to restart the container (e.g. after a reboot or restart of the Docker daemon):

        $ docker start mynodered

and stop it again when required:

        $ docker stop mynodered