---
title: "Material"
date: 2025-11-08T13:20:33+01:00
draft: false
layout: "single"
image: /hpcasia_logo.png
description: ""
toc: 
---

<aside class="notice">
  ⚠️ <strong>Take notice:</strong> You will need a specific environment using Docker for this tutorial.
</aside>
<p>
  <strong>Docker image needed:</strong> 
</p>

```
docker run -it ghcr.io/thomas-bouvier/numpex-pdi-tutorial:latest
```



This page source is the <a href="https://github.com/pdidev/tutorial/blob/tutorial_HPCAsia/How%20To.md">tutorial's 'How To'</a>.

To follow this tutorial you will need to get the Docker image and get the sources of the tutorial from Github:
```
git clone -b tutorial_HPCAsia https://github.com/pdidev/tutorial.git 
cd tutorial 
source ./spack_env/bootstrap_env.sh 
```
You may test that your environment is properly set up using the dedicated script:
```
./environment_check_script
[...]
[0] SUCCESS 
[1] SUCCESS
[2] SUCCESS
[3] SUCCESS
```

API used in this tutorial:

```C
PDI_status_t PDI_init(PC_tree_t conf) 
PDI_status_t PDI_finalize(PC_tree_t conf) 

PDI_status_t PDI_share(const char *name, const void *data, PDI_inout_t access)
PDI_status_t PDI_reclaim(const char *name)  

PDI_status_t PDI_expose(const char *name, const void *data, PDI_inout_t access) 
PDI_status_t PDI_multi_expose(const char *event_name, const char *name, 
                              const void *data, PDI_inout_t access, …) 

PDI_status_t PDI_access(const char *name, void **data, PDI_inout_t access) 
PDI_status_t PDI_release(const char *name)
```

You may now go through the <a href="https://github.com/pdidev/tutorial/blob/tutorial_HPCAsia/How%20To.md#1-pdi-hands-on">hands-on tutorial</a>.
