## Install a Helm chart to a cluster

```mermaid
---
title: Install a Helm chart to a cluster
---
graph LR
install_a_helm_chart_to_a_cluster["Install a Helm chart to a cluster"]
helm_path ---> install_a_helm_chart_to_a_cluster
kubeconfig ---> install_a_helm_chart_to_a_cluster
registry_username ---> install_a_helm_chart_to_a_cluster
registry_password ---> install_a_helm_chart_to_a_cluster
chart ---> install_a_helm_chart_to_a_cluster
version ---> install_a_helm_chart_to_a_cluster
name ---> install_a_helm_chart_to_a_cluster
namespace ---> install_a_helm_chart_to_a_cluster
values ---> install_a_helm_chart_to_a_cluster
```
## Inputs
| Name | Default | Required | Description |
| --- | --- | --- | --- |
| helm-path |  | True | The path to the helm binary to use |
| kubeconfig |  | True | A valid kubeconfig to connect to |
| registry-username |  | True | The registry username to log in with |
| registry-password |  | True | The registry password to use |
| chart |  | True | The chart to use |
| version |  | True | The version of the chart to install |
| name |  | True | The name of release to install |
| namespace |  | True | The namespace to install the application to |
| values |  | True | A values.yaml file to use |

## Outputs
| Name | Description |
| --- | --- |
