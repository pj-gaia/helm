# Gaia Dev Chart

This Helm chart bootstraps the full Gaia stack locally on Minikube for development. The chart spins up the `registry` backend (Strapi) and the `controller` frontend with a single `helm install` command.

## Prerequisites

*   [Minikube](https://minikube.sigs.k8s.io/docs/start/)
*   [Helm](https://helm.sh/docs/intro/install/)
*   [Docker](https://docs.docker.com/get-docker/)

## Local Development Workflow

1.  **Start Minikube:**
    ```bash
    minikube start
    ```

2.  **Point Docker to Minikube's daemon:**
    ```bash
    eval $(minikube docker-env)
    ```

3.  **Build both images locally:**
    Build the `registry` and `controller` images locally using their respective Dockerfiles.

4.  **Install the chart:**
    ```bash
    helm install gaia-dev ./gaia-dev -f gaia-dev/values.yaml
    ```

5.  **Access URLs:**
    Use the `minikube service` command to get the URLs for the `registry` and `controller` services.
    ```bash
    minikube service list
    ```
