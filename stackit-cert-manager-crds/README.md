# cert-manager CRDs

This directory contains the **CustomResourceDefinitions (CRDs)** required by [cert-manager](https://cert-manager.io/), downloaded directly from the official release.

## Why are the CRDs managed separately?

Although cert-manager’s Helm chart provides an option `installCRDs=true`, we **manage CRDs explicitly in Git and deploy them separately via ArgoCD** for the following reasons:

- **Safer Upgrades**: Helm does not reliably manage CRD upgrades. Changes to CRDs are not always applied automatically, which can result in broken behavior when updating cert-manager versions.
- **GitOps Transparency**: Storing CRDs in Git provides a full audit trail and makes changes visible in pull requests and diffs.


## How are these CRDs sourced?

They are downloaded from the [cert-manager GitHub releases](https://github.com/cert-manager/cert-manager/releases) using the following command:

```bash
export RELEASE_VERSION=v1.17.2  # Update to the desired version
curl -L -o cert-manager.crds.yaml https://github.com/cert-manager/cert-manager/releases/download/${RELEASE_VERSION}/cert-manager.crds.yaml
