# helm-starter

A helm3 plugin for managing [helm starters](https://helm.sh/docs/developing_charts/#chart-starter-packs). Helm starters
are used by the `helm create` command to customize the default chart. For example, an Istio starter can create
`VirtualService` and `DestinationRule` objects, in addition to the standard `Service` and `Deployment` objects.

Example helm starters:

* <https://github.com/salesforce/helm-starter-istio>
* <https://github.com/sitewards/helm-chart>
* <https://github.com/cloud104/helm-starter>

## Installation

```sh
> helm plugin install https://github.com/salesforce/helm-starter.git
```

## Usage

* `helm starter fetch GITURL [VERSION]`: Clones a bare helm starter repo into `$HELM_HOME/starters`
* `helm starter list`: Lists all the starters in `$HELM_HOME/starters`
* `helm starter update NAME [VERSION]`: Refresh an installed Helm starter or update to a specific version
* `helm starter delete NAME`: Delete `name` from `$HELM_HOME/starters`
* `helm starter inspect NAME`: Print out a starter's readme
* `helm starter --help`: print help

To use a starter, run:

```sh
> helm create NAME --starter STARTERNAME
```

## Example

```sh
> helm starter fetch https://github.com/salesforce/helm-starter-istio.git
> helm create banana-service --starter helm-starter-istio
```
