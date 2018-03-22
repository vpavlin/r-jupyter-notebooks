# Jupyter Notebook container image for R on OpenShift

This repository contains definition of Jupyter Notebook images with IRKernel enabled to perform computaions in R in JupyterHub running on top of OpenShift.

To deploy these images, you will first need to deploy and build minimal Python image from https://github.com/vpavlin/jupyter-notebooks

```
oc apply -f https://raw.githubusercontent.com/vpavlin/jupyter-notebooks/master/images.json
```

This will prepare the base Jupyter image for R images, which can be deployed and built the same way

```
oc apply -f https://raw.githubusercontent.com/vpavlin/r-jupyter-notebooks/master/images.json
```

If you then use our deployment of JupyterHub from https://github.com/AICoE/jupyterhub-ocp-oauth/, you should directly see the `s2i-r-minimal-notebook` in the list of available Jupyter Notebook images