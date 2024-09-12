# YM Import Resources

## Description
`ym import resources` is a composite action for importing resources.

## Author
Youmoni

## Inputs

| Name               | Type    | Required | Description                          |
|--------------------|---------|----------|--------------------------------------|
| `method`           | string  | true     | The import method                    |
| `environment`      | string  | true     | The environment to use               |
| `resources`        | string  | true     | Path to the resources                |
| `force`            | boolean | true     | Force import                         |
| `verbose`          | boolean | true     | Verbose output                       |
| `ym_version`       | string  | true     | YM version to use                    |
| `GITHUB_REPOSITORY`| string  | true     | GitHub repository name               |
| `DOCKERHUB_USERNAME` | string | true    | Docker Hub username                  |
| `DOMINO_CLIENT_ID` | string  | true     | Domino client ID                     |
| `DOMINO_USERNAME`  | string  | true     | Domino username                      |
| `AUTH0_CLIENT_ID`  | string  | true     | Auth0 client ID                      |
| `DOMINO_PASSWORD`  | string  | true     | Domino password                      |
| `DOMINO_CLIENT_SECRET` | string | true  | Domino client secret                 |
| `DOCKERHUB_TOKEN`  | string  | true     | Docker Hub token                     |
| `AUTH0_CLIENT_SECRET` | string | true   | Auth0 client secret                  |

## Usage

```yaml
jobs:
  import:
    runs-on: self-hosted
    steps:
      - name: Checkout repo
        uses: actions/checkout@v4
      - name: run ym-import
        uses: Youmoni/actions/ym-import@v1
        with:
          method: ${{ inputs.method }}
          environment: ${{ inputs.environment }}
          resources: ${{ inputs.resources }}
          verbose: ${{ inputs.verbose }}
          force: ${{ inputs.force }}
          ym_version: ${{ inputs.ym_version }}
          GITHUB_REPOSITORY: ${{ inputs.GITHUB_REPOSITORY }}
          DOCKERHUB_USERNAME: ${{ vars.DOCKERHUB_USERNAME }}
          DOMINO_CLIENT_ID: ${{ vars.DOMINO_CLIENT_ID }}
          DOMINO_USERNAME: ${{ vars.DOMINO_USERNAME }}
          AUTH0_CLIENT_ID: ${{ vars.AUTH0_CLIENT_ID }}
          DOMINO_PASSWORD: ${{ secrets.DOMINO_PASSWORD }}
          DOMINO_CLIENT_SECRET: ${{ secrets.DOMINO_CLIENT_SECRET }}
          DOCKERHUB_TOKEN: ${{ secrets.DOCKERHUB_TOKEN }}
          AUTH0_CLIENT_SECRET: ${{ secrets.AUTH0_CLIENT_SECRET }}
```