## Prepare Cluster

```mermaid
---
title: Prepare Cluster
---
graph LR
prepare_cluster["Prepare Cluster"]
app_slug["app-slug"]
api_token["api-token"]
namespace["namespace"]
chart["chart"]
yaml_dir["yaml-dir"]
kubernetes_distribution["kubernetes-distribution"]
kubernetes_version["kubernetes-version"]
license_id["license-id"]
cluster_name["cluster-name"]
ttl["ttl"]
disk["disk"]
nodes["nodes"]
min_nodes["min-nodes"]
max_nodes["max-nodes"]
instance_type["instance-type"]
timeout_minutes["timeout-minutes"]
node_groups["node-groups"]
tags["tags"]
ip_family["ip-family"]
kubeconfig_path["kubeconfig-path"]
export_kubeconfig["export-kubeconfig"]
helm_values["helm-values"]
helm_chart_name["helm-chart-name"]
helm_run_preflights["helm-run-preflights"]
kots_config_values["kots-config-values"]
kots_version["kots-version"]
kots_wait_duration["kots-wait-duration"]
kots_storage_class["kots-storage-class"]
customer_entitlements["customer-entitlements"]
helm_extra_repos["helm-extra-repos"]
cluster_id["cluster-id"]
cluster_kubeconfig["cluster-kubeconfig"]
app_slug ---> prepare_cluster
api_token ---> prepare_cluster
namespace ---> prepare_cluster
chart ---> prepare_cluster
yaml_dir ---> prepare_cluster
kubernetes_distribution ---> prepare_cluster
kubernetes_version ---> prepare_cluster
license_id ---> prepare_cluster
cluster_name ---> prepare_cluster
ttl ---> prepare_cluster
disk ---> prepare_cluster
nodes ---> prepare_cluster
min_nodes ---> prepare_cluster
max_nodes ---> prepare_cluster
instance_type ---> prepare_cluster
timeout_minutes ---> prepare_cluster
node_groups ---> prepare_cluster
tags ---> prepare_cluster
ip_family ---> prepare_cluster
kubeconfig_path ---> prepare_cluster
export_kubeconfig ---> prepare_cluster
helm_values ---> prepare_cluster
helm_chart_name ---> prepare_cluster
helm_run_preflights ---> prepare_cluster
kots_config_values ---> prepare_cluster
kots_version ---> prepare_cluster
kots_wait_duration ---> prepare_cluster
kots_storage_class ---> prepare_cluster
customer_entitlements ---> prepare_cluster
helm_extra_repos ---> prepare_cluster
prepare_cluster ---> cluster_id
prepare_cluster ---> cluster_kubeconfig
```
## Inputs
| Name | Default | Required | Description |
| --- | --- | --- | --- |
| app-slug |  | True | App Slug. |
| api-token |  | True | API Token. |
| namespace | default | True | The namespace to install the application to |
| chart |  | False | Path to the helm chart (One of `chart` or `yaml-dir` is required). |
| yaml-dir |  | False | The directory containing multiple yamls for a Replicated release. |
| kubernetes-distribution |  | True | Kubernetes distribution of the cluster to provision. |
| kubernetes-version |  | False | Kubernetes version to provision (format is distribution dependent). |
| license-id |  | False | License ID to use for the installation (required for Embedded Cluster distribution). |
| cluster-name |  | False | Name of the cluster to provision |
| ttl |  | False | Cluster TTL (duration, max 48h) |
| disk |  | False | Disk size in GiB |
| nodes |  | False | Number of nodes to provision |
| min-nodes |  | False | Minimum number of nodes to provision |
| max-nodes |  | False | Maximum number of nodes to provision |
| instance-type |  | False | Instance type to provision |
| timeout-minutes | 20 | False | Time to wait for the cluster to have a status of `running` |
| node-groups |  | False | Node groups to provision.<br>Example:<br><pre>node-groups: \|<br>  - name: "worker"<br>    instance-type: "t3.medium"<br>    disk: 100<br>    nodes: 3</pre><br> |
| tags |  | False | Tags to assign to the cluster.<br>Example:<br><pre>tags: \|<br>  - key: "department"<br>    value: "engineering"</pre><br> |
| ip-family |  | False | IP Family to use for the cluster (ipv4, ipv6 or dual) |
| kubeconfig-path |  | False | If specified, the kubeconfig will be written to this path |
| export-kubeconfig | false | False | Export the KUBECONFIG variable (true/false) |
| helm-values |  | False | A Helm values.yaml file to use |
| helm-chart-name |  | False | The name of the Helm chart to use |
| helm-run-preflights | true | False | Run preflight checks (true/false) |
| kots-config-values |  | False | The KOTS config values to use |
| kots-version | latest | False | The version of KOTS to use |
| kots-wait-duration |  | False | Timeout for KOTS to be used while waiting for individual components to be ready. must be in Go duration format (eg: 10s, 2m) (default "2m") |
| kots-storage-class |  | False | Sets the storage class to use for the KOTS Admin Console components. Default: unset, which means the default storage class will be used. |
| customer-entitlements |  | False | Entitlements to assign to the customer.<br>Example:<br><pre>customer-entitlements: \|<br>  - name: "number-of-users"<br>    value: "10"</pre><br> |
| helm-extra-repos |  | True | Extra helm repos to add.<br>Example:<br><pre>helm-extra-repos: \|<br>  - repo_name: "cnpg"<br>    url: "https://cloudnative-pg.github.io/charts"<br>    namespace: "cnpg-system"<br>    chart_name: "cloudnative-pg"<br>  - repo_name: "minio-operator"<br>    url: "https://operator.min.io"<br>    namespace: "minio-operator"<br>    chart_name: "operator"</pre><br> |

## Outputs
| Name | Description |
| --- | --- |
| cluster-id | Contains the cluster id. |
| cluster-kubeconfig | Contains the kubeconfig to connect with the cluster. |

