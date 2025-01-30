# Introduction

## Overview

The Gravitee Kubernetes Operator (GKO) is a [Kubernetes Operator](https://kubernetes.io/docs/concepts/extend-kubernetes/operator/) developed by Gravitee that provides the ability to manage Gravitee APIs, applications and other assets in a Kubernetes-native and declarative way.&#x20;

GKO allows APIs and other resources to be managed "as-code", unlocking the possibility to implement GitOps workflows that provide high levels of automation, reliability, and collaboration in the way you manage your API platform.

GKO is designed to be used in combination with the Gravitee API Management Console, Developer Portal, and Gateway. APIs and Applications are examples of resources that GKO can manage and synchronize with the rest of the Gravitee platform.

Resources that are managed by GKO can be synchronized with the API Management control plane but will be displayed as read-only. This is to enforce the fact that the source of truth for these resources is coming from the Operator, and not from the GUI.&#x20;

Choose from the guides below to get started with the Gravitee Kubernetes Operator.

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td>Quickstart guide</td><td></td><td><a href="../4.x/getting-started/quickstart-guide.md">quickstart-guide.md</a></td></tr><tr><td></td><td>Install with Helm</td><td></td><td><a href="../4.x/getting-started/installation/">installation</a></td></tr><tr><td></td><td>Custom Resource Definition introduction</td><td></td><td><a href="../4.x/overview/custom-resource-definitions/">custom-resource-definitions</a></td></tr><tr><td></td><td>Reference architecture</td><td></td><td><a href="../4.x/overview/example-architecture.md">example-architecture.md</a></td></tr><tr><td></td><td>API reference</td><td></td><td><a href="../4.x/overview/example-architecture.md">example-architecture.md</a></td></tr></tbody></table>
