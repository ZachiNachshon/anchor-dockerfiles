# Anchor Dockerfiles
A curated list of `dockerfiles` that act as an example repository for [Anchor](https://github.com/ZachiNachshon/anchor) utility.

![docker-logo](assets/logos/docker-logo-resized-500px.png) 

## What is it?
This repository acts as one stop shop for all Dockerfiles & Kubernetes manifests that comprise your development environment.<br/>
Its structure is tight to [Anchor](https://github.com/ZachiNachshon/anchor) requirements for proper integration.<br/>

## How does it work?
#### Environment Variables
`Anchor` relies on a `DOCKER_FILES` environment variable that points to a local directory path containing the `dockerfiles` and k8s manifests. 

#### Directory Structure
Every directory within this repository must contain the following structure:

    .
    ├── ...
    ├── nginx                   # Name of the docker image/container
    │   └── k8s                 # Optional: Kubernetes content
    │       └── manifest.yaml   # Optional: Kubernetes manifest
    │   ├── Dockerfile          # Dockerfile with build/run/tag/push instructions
    │   ├── .env                # Optional: Override root `NAMESPACE` & `TAG` environment vars and/or add your own
    │   └── ...                 # Optional: files for docker build
    ├── ... 
    └── .env                    # Optional: Override default `NAMESPACE` & `TAG` environment vars and/or add your own at root level                 
    
> It is recommended to back the `DOCKER_FILES` directory by a git repository

##### Affinity
It is possible to place the directory structure within a parent directory.<br/>
The parent directory name would then be treated as the directory affinity.<br/>
For example, we could place the `nginx` directory within a `web-server` parent directory.<br/>
As a result, the `anchor list` output shall be:
```bash
| #  | NAME      DOCKERFILE      K8S_MANIFEST      AFFINITY
| 1  | nginx        yes              yes           web-server
```    

##### Customization
The following environment variables can be overridden by setting these on one of the `.env` files:
- `export NAMESPACE="my-namespace"`
- `export TAG="v1.1.0"`

> Default values are `anchor` namespace and `latest` tag

#### Dockerfile Instructions
Every `Dockerfile` must have the following header is order to integrate properly to `Anchor`:
```bash
# OVERVIEW
# --------
# This is the Dockerfile for nginx
#
# REQUIRED BASE IMAGE TO BUILD THIS IMAGE
# ---------------------------------------
# None.
#
# REQUIRED FILES TO BUILD THIS IMAGE
# ----------------------------------
# (1) None.
#
# HOW TO BUILD THIS IMAGE
# -----------------------
# docker build -f Dockerfile \
#              -t ${NAMESPACE}/nginx:${TAG} \
#              .
#
# HOW TO RUN THIS CONTAINER
# -------------------------
# docker run -t -d \
#            -v ${HOME}/.nginx/nginx.conf:/etc/nginx/nginx:ro \
#            --name=${NAMESPACE}-nginx \
#            -p 8080:80 \
#            ${NAMESPACE}/nginx:${TAG}
#
# HOW TO TAG THIS IMAGE
# ---------------------
# docker tag ${NAMESPACE}/nginx:${TAG} \
#            ${REGISTRY}/${NAMESPACE}/nginx:${TAG}
#
# HOW TO PUSH THIS IMAGE
# ----------------------
# docker push ${REGISTRY}/${NAMESPACE}/nginx:${TAG}
#
```

> Note:<br/>
> `docker tag` and `docker push` are mandatory only if resources should be deployed to kubernetes.  

#### Kubernetes Manifest
`Anchor` is using a standard kubernetes manifest.<br/>
It supports environment variables substitution within manifests using `envsubst`.<br/>
In order to properly expose the deployed manifest to the host, a port-forward declaration is needed on the `manifest.yaml`:

```bash
# HOW TO EXPOSE THIS MANIFEST
# ---------------------------
# kubectl port-forward -n ${NAMESPACE} deployment/nginx 1234:80
#
```