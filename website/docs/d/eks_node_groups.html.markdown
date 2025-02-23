---
subcategory: "EKS"
layout: "aws"
page_title: "AWS: aws_eks_node_groups"
description: |-
  Provides a set of node groups for an EKS Cluster
---

# Data Source: aws_eks_node_groups

Retrieve the EKS Node Groups associated with a named EKS cluster. This will allow you to pass a list of Node Group names to other resources.

## Example Usage

```terraform
data "aws_eks_node_groups" "example" {
  cluster_name = "example"
}

data "aws_eks_node_group" "example" {
  for_each = data.aws_eks_node_group_names.example.names

  cluster_name    = "example"
  node_group_name = each.value
}
```


## Argument Reference

* `cluster_name` - (Required) The name of the cluster.

## Attributes Reference

* `id` - Cluster name.
* `names` - A set of all node group names in an EKS Cluster.
