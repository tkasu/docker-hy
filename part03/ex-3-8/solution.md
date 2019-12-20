# docker-hy, Ex 3.8b

Project: [imdb-list-analyzer](https://github.com/tkasu/imdb-list-analyzer/tree/ecd59016eacbfb4a4840edacc50a84ddfd94603b)

## Install guide

See README.md -> Usage -> Web GUI -> Deployment -> Google Cloud Platofrm with Cloud Build CI/CD and Kubernetes

## Automated infrastructure building and app ci/cd pipeline using Google Cloud Platform, Kubernetes, Docker and Terraform

I built infrastructure building tool using Docker and Terraform. To deploy application, only Docker (and optionally gcloud) is needed, as Terraform is initialized inside a container (using Dockerfile.infra). Infrastructure state are saved to local disk using Docker volume mounts. To ease up the usage, following helper scripts can be used:

    * infra_build_image.sh
    * infra_plan.sh
    * infra_create.sh
    * infra_destroy.sh

The GCP pipeline works as follows:

    1. When code will be pushed to GCP Source repository, GCP Cloud Build will trigger
    2. Cloud Build will: 
        * Build Dockerfile.slim
        * Push image to GCP Conainer Registery
        * Deploy built image to Google Kubernetes Engine
        * Deploy load balancer work the deployed app

