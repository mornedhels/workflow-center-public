# Docker Trivy Workflow

> [docker-trivy.yml](../../.github/workflows/docker-trivy.yml)

This workflow scans a Docker image with trivy and reports the result to GitHub Security.

## Usage

```yaml
jobs:
  docker-build:
    uses: mornedhels/workflow-center-public/.github/workflows/docker-trivy.yml@main
    with:
      image-name: my-image
```

## Parameters

| Name                    | Required | Default                   | Description                                                   |
|-------------------------|:--------:|---------------------------|---------------------------------------------------------------|
| image-name              |    *     |                           | Name of the image to build                                    |
| image-tag               |          |                           | Tag of the image to build (can be multiple), e.g. `dev,1.0.0` |
| container-registry      |          | `registry.hub.docker.com` | The container registry to push the image to                   |
| container-registry-user |          | `mornedhels`              | The container registry user to push the image to              |
| trivy-ignore-unfixed    |          | `true`                    | Whether to ignore unfixed vulnerabilities in trivy            |
| runner                  |          | `ubuntu-latest`           | The GitHub runner to use                                      |

## Secrets

| Name                        | Required | Description                                  |
|-----------------------------|:--------:|----------------------------------------------|
| CONTAINER_REGISTRY_PASSWORD |          | The password for the container registry user |
