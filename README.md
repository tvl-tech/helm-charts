# Helm Chart Repository

Helm chart repository for housing helm charts.
Charts are served from the docs directory.

## How to package and publish a new chart

- Create chart scaffolding `helm create <chart-name>`
- Package chart into docs directory `helm package <chart-name> --destination docs`
- Update repository index `helm repo index docs --url https://tvl-tech.github.io/helm-charts`
- Commit and push to remote Github repository `git add . && git commit -m "feat: add <chart-name> chart" && git push origin main`

## Updating a chart

- (Re)package recently updated chart `helm package <chart-name> --destination docs`
- Update repository index `helm repo index docs --url https://tvl-tech.github.io/helm-charts`
- Commit and push to remote Github repository `git add . && git commit -m "feat: updated <chart-name> chart" && git push origin main`

## Using a published chart

- Add the repository (client-side) `helm repo add <repo-name> <repo-url>`
- Update the repository (client-side) `helm repo update`
- Install the chart with `helm upgrade --install <release-name> <chart-url>`
