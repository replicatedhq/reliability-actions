## Create Cluster

```mermaid
---
title: Create Cluster
---
graph LR
create_cluster["Create Cluster"]
api_token["api-token"]
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
cluster_id["cluster-id"]
cluster_kubeconfig["cluster-kubeconfig"]
api_token ---> create_cluster
kubernetes_distribution ---> create_cluster
kubernetes_version ---> create_cluster
license_id ---> create_cluster
cluster_name ---> create_cluster
ttl ---> create_cluster
disk ---> create_cluster
nodes ---> create_cluster
min_nodes ---> create_cluster
max_nodes ---> create_cluster
instance_type ---> create_cluster
timeout_minutes ---> create_cluster
node_groups ---> create_cluster
tags ---> create_cluster
ip_family ---> create_cluster
kubeconfig_path ---> create_cluster
export_kubeconfig ---> create_cluster
create_cluster ---> cluster_id
create_cluster ---> cluster_kubeconfig
```
## Inputs
| Name | Default | Required | Description |
| --- | --- | --- | --- |
| api-token |  | True | API Token. |
| kubernetes-distribution |  | True | Kubernetes distribution of the cluster to provision. |
| kubernetes-version |  | False | Kubernetes version to provision (format is distribution dependent). |
| license-id |  | False | License ID to use for the installation (required for Embedded Cluster distribution). |
| cluster-name |  | False | Name of the cluster to provision |
| ttl |  | False | Cluster TTL (duration, max 48h) |
| disk |  | False | Disk size in GiB |
| nodes |  | False | Number of nodes to provision |
| min-nodes |  | False | Minimum number of nodes to provision |
| max-nodes |  | False | Maximum number of nodes to provision |
| instance-type |  | False | Instance type to provision (ignored if you specify node-groups) |
| timeout-minutes | 20 | False | Time to wait for the cluster to have a status of `running` |
| node-groups |  | False | Node groups to provision.<br>Example:<br><pre>node-groups: \|<br>  - name: "worker"<br>    instance-type: "t3.medium"<br>    disk: 100<br>    nodes: 3</pre><br> |
| tags |  | False | Tags to assign to the cluster.<br>Example:<br><pre>tags: \|<br>  - key: "department"<br>    value: "engineering"</pre><br> |
| ip-family |  | False | IP Family to use for the cluster (ipv4 or dual (kind clusters only)) |
| kubeconfig-path |  | False | If specified, the kubeconfig will be written to this path |
| export-kubeconfig | false | False | Export the KUBECONFIG variable (true/false) |

## Outputs
| Name | Description |
| --- | --- |
| cluster-id | Contains the cluster id. |
| cluster-kubeconfig | Contains the kubeconfig to connect with the cluster. |

