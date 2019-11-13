---
date: 2019-10-23
linktitle: "Channels And Releases"
title: Channels And Releases
weight: 20020
---

The [Replicated vendor portal](https://vendor.replicated.com) provides a software developer with a location to create and release versions of an application to various release channels. The vendor portal includes a YAML editor with online policy validation of YAML to help validate that the YAML is both valid and will meet end-user requirements.

## Promoting Releases
Once a release is ready to be installed, the release can be promoted to one or more release channels. More details can be found in the [Promote Releases documentation](../promoting-releases).

## Manage Release Channels
By default, there are 3 release channels: Stable, Beta and Unstable. After logging in to Replicated and select the Channels tab, these channels will be automatically created. You can delete, edit or create new channels at any time. The channels Replicated creates by default are commonly used for:

### Unstable
The Unstable channel is designed to constantly push releases to, much in the same way that CI continuously deploy new versions to a cloud product. This is the channel that a development environment should have a license assigned to. This channel is designed to be internal and for testing, not for customers to be licensed against.

### Beta
The Beta channel is created for release candidates and early adopting customers. We recommend promoting a release to the Beta channel once it’s passed automated testing in the Unstable channel. It's also common to license some early-adopting customers against this channel.

### Stable.
Most end customers will have licenses that's are assigned to the Stable channel. By doing so, they’ll only receive updates when a new release is pushed to the Stable channel.
