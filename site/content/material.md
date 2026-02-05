---
title: "Material"
date: 2025-11-08T13:20:33+01:00
draft: false
layout: "single"
image: /hpcasia_logo.png
description: ""
toc: 
---

⚠️ Take notice: This tutorial requires a working container environment using [Docker](https://docs.docker.com/engine/install/) or [Podman](https://podman.io/docs/installation).

⚠️ Prior to the start of the tutorial session, to avoid overwhelming the venue's wifi, you may download the docker/podman container image using the following command: 
`docker pull ghcr.io/thomas-bouvier/numpex-pdi-tutorial:latest`


# Container environment

## Using an embedded text editor (vim/nano) 

```shell
docker run -it ghcr.io/thomas-bouvier/numpex-pdi-tutorial:latest
vim
```

## Using your own IDE (eg: vscode)

If you want to use your own IDE, you may bind-mount a local folder to the container:

```shell
# move to a folder in which to git clone (eg: cd /tmp).
git clone git@github.com:pdidev/tutorial.git -b tutorial_HPCAsia
podman run -it -u root -v tutorial:/opt/tutorial ghcr.io/thomas-bouvier/numpex-pdi-tutorial:latest
```

You may now open the cloned tutorial folder with your favorite IDE.


## Checking your environment

From within the container environment, you may test that your setup is working using the dedicated script from the tutorial folder:

```shell
./environment_check_script
[...]
[0] SUCCESS 
[1] SUCCESS
[2] SUCCESS
[3] SUCCESS
```


# Deisa

```shell
docker run -it -u root -p 8787:8787 -v <TUTORIAL_FOLDER>:/tutorial ghcr.io/thomas-bouvier/numpex-pdi-tutorial:latest
```

The container image, by default, runs rootless. A `pdi` user is created and used within the container.
When using podman, and to avoid access rights on bind-mounted volumes, you may set the running user as root by specifying `-u root`.
This will run as root inside the container and as the current user (`id -u`) from the host.
You may check this using: `podman top -l user huser`

The docker/podman command will map local port 8787 to the container's port 8787 that is used by the Dask dashboard.
You may change the local port to another port.
