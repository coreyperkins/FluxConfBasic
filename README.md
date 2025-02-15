# Confluence ProtoType

The point of this exercise is to deploy Confluence using Kustomize on localhost (KIND cluster and Podman only).

Use a KIND cluster
Install FluxCD

1. Export vars for FluxCD
    - export GITHUB_TOKEN=<YOUR GH TOKEN>
    - export GITHUB_USER=<YOUR GH USER>

1. Bootstrap Flux to your repo:

`flux bootstrap github \
  --owner=$GITHUB_USER \
  --repository=FluxConfBasic \
  --branch=main \
  --path=./clusters/my-cluster \
  --personal`

Create a Kustomization + HelmRelease to install Confluence with basic resources
- emptyDir for sharedHome and localHome volumes

At the end of this exercise, try to deploy to Gravity's sandbox.