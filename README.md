# Kube Eagle Helm Chart

Helm chart for deployment of kube-eagle in Kubernetes.

## Installing helm chart

```bash
helm repo add kube-eagle https://raw.githubusercontent.com/cloudworkz/kube-eagle-helm-chart/master
helm repo update
helm install kube-eagle kube-eagle/kube-eagle
```

If using helm version 2 : 

```bash
helm install --name=kube-eagle kube-eagle/kube-eagle
```

## Chart configuration

| Parameter                         | Description                                                        | Default               |
| --------------------------------- | ------------------------------------------------------------------ | --------------------- |
| `rbac.create`                     | Create and use role based access resources                         | `true`                |
| `telemetry.host`                  | Host for prometheus server to to listen on                         | `0.0.0.0`             |
| `telemetry.port`                  | Port for prometheus server to listen on                            | `8080`                |
| `serviceMonitor.create`           | Whether or not to create a service monitor for prometheus operator | `false`               |
| `serviceMonitor.interval`         | Scrape interval for prometheus operator                            | `10s`                 |
| `serviceMonitor.scrapeTimeout`    | Scrape timeout for prometheus operator                             | `10s`                 |
| `serviceMonitor.releaseLabel`     | Release label being used for prometheus operator selector          | `prometheus-operator` |
| `serviceMonitor.additionalLabels` | Additional labels to add to the ServiceMonitor                     |                       |
| `metricsNamespace`                | Prefix of exposed prometheus metrics                               | `eagle`               |
| `logLevel`                        | Logger's log granularity (debug, info, warn, error, fatal, panic)  | `info`                |
| `podSecurityContext.runAsUser`    | UserID to use for the pod                                          | `99`                  |
| `podSecurityContext.runAsUser`    | User group to use for the pod                                      | `99`                  |
| `containerSecurityContext`        | Security Context for the kube eagle container                      | `{}`                  |
| `podAnnotations`                  | Pod annotations                                                    | `{}`                  |
| `priorityClassName`               | Priority Class to be used by the pod                               | `""`                  |
| `env`                             | Additional environment variables                                   | `{}`                  |
