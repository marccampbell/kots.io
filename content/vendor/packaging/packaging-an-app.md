---
date: 2019-10-23
linktitle: "Overview"
title: Packaging An Application
weight: 20010
---

A KOTS application is a Kubernetes application that is designed for day-2 operations. KOTS applications include preflight checks for conformance testing, support bundle collectors for debugging, analyzers for remediation of problems, per-customer licensing, private images, config screens and more. When packaged using the [Replicated Vendor Portal](https://vendor.replicated.com), a KOTS application can be installed to an existing Kubernetes cluster or Kubernetes can be included with the installer.

## Installation

When installing a KOTS application, customizable preflight checks test a cluster for necessary resources or other dependencies, and show warnings or errors if the target cluster fails any of these checks.  The Application specs provide branding metadata (icon, title, descriptions, etc...), readiness checks, and end-user links, enabling the Admin Console to show application health and readiness and launch the application once it's ready.

KOTS licenses are created and managed through the Replicated [Vendor Portal](https://vendor.replicated.com), which supports product assortment and differentiation with configurable entitlements, expiration dates, and license types.

The Config spec controls a dynamic configuration page which collects site-specific values from the operator and exposes generated values such as internal access tokens and connection strings.

## Day-2 Operations

The Support Bundle spec controls the collection and analysis of diagnostic info to simplify troubleshooting application issues.

Application updates can be reviewed and audited before they're applied.  Release Notes from the Application spec provide a high-level description of each release, and the Admin Console dashboard provides a version history and diff viewer to highlight any changes in deployment specs from one version to the next.

## Getting Started

To get started creating a KOTS application, bring a Kubernetes application to the [Vendor Portal](https://vendor.replicated.com) and create a new application. 
