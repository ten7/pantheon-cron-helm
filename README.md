# pantheon-cron-helm

A helm chart execute tasks on your Pantheon sites via Terminus on Kubernetes.

## How it works

This chart provisions a cronjob which runs the [`ten7/pantheon-cron`](https://hub.docker.com/repository/docker/ten7/pantheon-cron) container. It uses the [`terminus`](https://pantheon.io/docs/terminus) command execute one or more tasks on your Patheon sites.

## Features

* Uses Pantheon's own tools to interact with your site
* Multiple commands can be executed in sequence
* Multiple sites can be interacted with from a single helm release
* Can be installed multiple times in the same namespace, with different schedules and command sets

## Requirements

* A `terminus` Machine Token must be provisioned for the site.
* The SSH private and public key must be available to the container.

## Installation

```shell
helm repo add pantheon-cron https://ten7.github.io/pantheon-cron-helm/
helm repo update
helm upgrade --install pantheon-cron pantheon-cron/pantheon-cron --namespace=my-namespace -f path/to/my-values.yml
```

## Configuration

For a full list of values, see [values.yaml](https://raw.githubusercontent.com/ten7/pantheon-cron-helm/main/charts/pantheon-cron/values.yaml).

## License

This chart is licensed under GPLv3. See [LICENSE](https://raw.githubusercontent.com/ten7/pantheon-cron-helm/main/LICENSE) for the complete language.
