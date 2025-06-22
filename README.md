# About

GitHub Action to run [`buildcharts generate`](https://github.com/eddietisma/buildcharts) inside a Docker container.

This action uses the BuildCharts CLI to generate CI/CD pipelines from a **declarative `build.yaml` file**. 

- Reads your declarative `build.yaml`.
- Generates a pipeline using `docker-bake.hcl`.

## Usage

```yaml
name: ci

on:
  push:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Set up BuildCharts
        uses: buildcharts/setup-action@v1

      - name: Generate BuildCharts pipeline
        uses: buildcharts/generate-action@v1
```