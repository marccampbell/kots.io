---
date: 2019-10-09
linktitle: "GitOps Workflows"
title: Pushing Updates to a GitOps Workflow
weight: 10020
draft: false
---

While the Admin Console is initially configured to receive updates, show the changes and deploy them to the cluster, this process can be changed and converted to use a GitOps workflow instead. When using a GitOps workflow, changes from the Admin Console (config changed, upstream updates, license updates) will be pushed to a private Git repository, where an existing CI/CD process can execute to deliver the manifests to the cluster.

To begin migrating to a GitOps deployment workflow, click the GitOps link at the top of the Admin Console.

![GitOps](/images/gitops.png)

Continuing, choose the Git provider, repo, and optionally branch and path to commit to in the repo.

![GitOps Provider](/images/gitops-provider.png)

Finally, select the action to take when there's an update. The Admin Console can either create a new commit to the branch specified, or it can create a Pull/Merge Request (if supported by the provider). On this screen, there's an option to choose what type of asset to deliver to the git repo.

Selecting "Rendered YAML" will result in a single, multi-doc YAML file being committed to the repo. This is useful for legacy clusters, or GitOps deploy tools that don't yet support [Kustomize](https://kustomize.io). For modern (> 1.14) Kubernetes clusters and tools that run `kubectl` 1.14 or later, it's recommended to choose the "Full Kustomizable Output" option. This will create a `kustomization.yaml` in the commit/pull request that can then be passed to `kubectl apply -k`.

![GitOps Action](/images/gitops-action.png)

Once GitOps is set up, a new "GitOps" tab will be available on the application. This tab contains a public deploy key. The private key will be stored securely in the Admin Console. Add the deploy key to the repo, and verify that the Admin Console can connect by clicking the Test button.

## First commits

After converting to GitOps, the Admin Console will make a commit/pull request with the current version that's "Deployed". Then, it will make separate commits (or a single pull request) with any pending updates that have not been deployed from the Admin Console.
