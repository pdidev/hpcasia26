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

# Container environment

```
docker run -it ghcr.io/thomas-bouvier/numpex-pdi-tutorial:latest
```

From within the container environment, you may test that your setup is working using the dedicated script:

```
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
pip install deisa-dask matplotlib
```

The container image, by default, runs rootless. A `pdi` user is created and used within the container.
When using podman, and to avoid access rights on bind-mounted volumes, you may set the running user as root by specifying `-u root`.
This will run as root inside the container and as the current user (`id -u`) from the host.
You may check this using: `podman top -l user huser`

The docker/podman command will map local port 8787 to the container's port 8787 that is used by the Dask dashboard.
You may change the local port to another port.


