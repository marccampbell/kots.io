---
date: 2019-10-23
linktitle: "Overview"
title: Embedded Kubernetes
description: "A Kots application can be deployed to an existing cluster or the installer can provision a new cluster with the application."
weight: 20090
---

A KOTS application can be deployed to an existing cluster or the installer can provision a new cluster with the application.

To create an installer, visit the "Kubernetes Installer" link in the [Vendor Portal](https://vendor.replicated.com). From here, you can create a YAML document that describes the version of Kubernetes and the components that you'd like to include in your installer.

```yaml
apiVersion: kurl.sh/v1beta1
kind: Installer
metadata:
  name: "my-installer"
spec:
  kubernetes:
    version: "latest"
  docker:
    version: "latest"
  weave:
    version: "latest"
  rook:
    version: "latest"
  contour:
    version: "latest"
  kotsadm:
    version: "latest"
```

## Add Ons

The installer supports various add-ons. Removing an add-on from the spec will remove the application from being included in your installer. For a full list of supported add-ons, see the [reference documentation](/reference/kubernetes-installers/kurl/).

## Add-On Versions

Add-ons that are using `version: "latest"` will be pinned to the latest version of the component that is supported by the installer. This means that when an update to the component is shipped, the installer will automatically be updated. This may be desirable in some scenarios, while other installers may want to have tested, reproducible and predictable installed versions. To support this use case, the YAML specification allows for specifying an exact version instead of using "latest".

## Advanced Options

In addition to the standard YAML, many add-ons offer optional, advanced options that will be used as defaults during installation.

```yaml
apiVersion: kurl.sh/v1beta1
kind: Installer
metadata:
  name: "my-installer"
spec:
  kubernetes:
    version: "latest"
  weave:
    version: "latest"
    IPAllocRange: "10.10.0.0/16"
  rook:
    version: "latest"
  contour:
    version: "latest"
  kotsadm:
    version: "latest"
```

Most add-ons support some advanced options. For a full list of these supported options, see the [reference documentation](/reference/kubernetes-installers/kurl/).

## Operating Systems

The installer will support the following operating systems:

* Ubuntu 18.04
* Ubuntu 16.04
* Red Hat Enterprise Linux 7.4 - 7.6
* CentOS 7.4 - 7.6
