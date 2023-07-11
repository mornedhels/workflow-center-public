# Docker Build Workflow

> [docker-build.yml](../../.github/workflows/docker-build.yml)

This workflow builds a Docker image and pushes it to a container registry.

## Usage

```yaml
jobs:
  docker-build:
    uses: mornedhels/workflow-center-public/.github/workflows/docker-build.yml@main
    with:
      image-name: my-image
      image-tag: |
        dev
    secrets:
      CONTAINER_REGISTRY_PASSWORD: ${{ secrets.CONTAINER_REGISTRY_PASSWORD }}
```

## Parameters

| Name                    | Required | Default                   | Description                                                                  |
|-------------------------|:--------:|---------------------------|------------------------------------------------------------------------------|
| image-name              |    *     |                           | Name of the image to build                                                   |
| image-tag               |    *     |                           | Tag of the image to build (can be multiple), e.g. `dev,1.0.0`                |
| dockerfile              |          | `Dockerfile`              | Path to the Dockerfile                                                       |
| platform                |          | `linux/amd64`             | Platform to build for                                                        |
| build-args              |          |                           | Build args for the docker build step (add leading \| to work e.g. image-tag) |
| buildx-version          |          |                           | The version of buildx to use. If not given, the latest version is used       |
| container-registry      |          | `registry.hub.docker.com` | The container registry to push the image to                                  |
| container-registry-user |          | `mornedhels`              | The container registry user to push the image to                             |
| trivy-scan              |          | `true`                    | Whether to scan the image with trivy                                         |
| trivy-ignore-unfixed    |          | `true`                    | Whether to ignore unfixed vulnerabilities in trivy                           |
| project-root            |          | `.`                       | The root of the project                                                      |
| runner                  |          | `ubuntu-latest`           | The GitHub runner to use                                                     |

## Secrets

| Name                        | Required | Description                                  |
|-----------------------------|:--------:|----------------------------------------------|
| CONTAINER_REGISTRY_PASSWORD |    *     | The password for the container registry user |
