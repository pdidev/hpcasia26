---
title: "Material"
date: 2025-11-08T13:20:33+01:00
draft: false
layout: "single"
image: /hpcasia_logo.png
description: ""
toc: 
---

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

<div style="font-weight:bold; font-size:1.25rem; margin-top:1rem;">
API used in this tutorial
</div>

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

<div style="font-weight:bold; font-size:1.25rem; margin-top:1rem;">
External links
</div>

<a href="https://pdi.dev/hpcasia26">Link to HPCAsia PDI tutorial webpage</a>

<a href="https://pdi.dev">Link to PDI official webpage</a>

<a href="https://github.com/pdidev/pdi/">Link to PDI official GitHub repo</a>

<a href="https://pdidev.slack.com/">Link to PDI Slack channel</a>

<div style="font-weight:bold; font-size:1.25rem; margin-top:1rem;">
Acknowledgements
</div>
As part of the "France 2030" initiative, this work has benefited from a State grant managed by the French National Research Agency (Agence Nationale de la Recherche) attributed to the Exa-DoST project of the NumPEx PEPR program, reference: ANR-22-EXNU-0004.

Part of the research presented here has received funding from the Horizon 2020 (H2020) funding framework under grant/award number: 676629 (EoCoE) and 824158 (EoCoE-II). The present publication reflects only the authors views. The European Commission is not liable for any use that might be made of the information contained therein.


You may now go through the <a href="https://github.com/pdidev/tutorial/blob/tutorial_HPCAsia/How%20To.md#1-pdi-hands-on">hands-on tutorial</a>.
