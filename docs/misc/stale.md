# Close stale issues

> [stale.yml](../../.github/workflows/stale.yml)

This workflow closes stale issues and PRs.

## Usage

```yaml
jobs:
  stale:
    permissions:
      issues: write
      pull-requests: write
    uses: mornedhels/workflow-center-public/.github/workflows/stale.yml@main
```

## Parameters

| Name                    | Required | Default                   | Description                                                   |
|-------------------------|:--------:|---------------------------|---------------------------------------------------------------|

## Secrets

| Name                        | Required | Description                                  |
|-----------------------------|:--------:|----------------------------------------------|
