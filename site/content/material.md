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

## Container environment

#### To use the embedded IDE

```
docker run -it ghcr.io/thomas-bouvier/numpex-pdi-tutorial:latest
```

#### To use your own IDE

If you want to use your own IDE, you can do in a first terminal:

```
mkdir <path>/<to>/<your>/<folder>
cd <path>/<to>/<your>/<folder>
git clone git@github.com:pdidev/tutorial.git -b tutorial_HPCAsia

```
And from another terminal:
```
cd <path>/<to>/<your>/<folder>/tutorial
podman run -it -u root -v ${PWD}:/opt/tutorial ghcr.io/thomas-bouvier/numpex-pdi-tutorial:latest
```
For example, from this second terminal, doing `code .` will allow to do the tutorial from VS Code. 

#### To check your environment

From within the container environment, you may test that your setup is working using the dedicated script:

```
./environment_check_script
[...]
[0] SUCCESS 
[1] SUCCESS
[2] SUCCESS
[3] SUCCESS
```


## Deisa

```shell
docker run -it -u root -p 8787:8787 -v <TUTORIAL_FOLDER>:/tutorial ghcr.io/thomas-bouvier/numpex-pdi-tutorial:latest
pip install deisa-dask matplotlib
```

The container image, by default, runs rootless. A `pdi` user is created and used within the container.
When using podman, and to avoid access rights on bind-mounted volumes, you may set the running user as root by specifying `-u root`.
This will run as root inside the container and as the current user (`id -u`) from the host.
You may check this using: `podman top -l user huser`

The docker/podman command will map local port 8787 to the container's port 8787 that is used by the Dask dashboard.
You may change the local port to another port.


