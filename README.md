# Sandbox Helm Charts

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Chart Publish](https://github.com/clhain/sandbox-helm-charts/actions/workflows/release.yml/badge.svg?branch=main)](https://github.com/clhain/sandbox-helm-charts/actions/workflows/release.yml)

## Usage

[Helm](https://helm.sh) must be installed to use the charts.  Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

  helm repo add sandbox-charts https://clhain.github.io/sandbox-helm-charts

If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages.  You can then run `helm search repo
sandbox-charts` to see the charts.

To install the sandbox-base chart:

    helm install sandbox-base sandbox-charts/sandbox-base

To uninstall the sandbox-base chart:

    helm delete sandbox-base

To install the sandbox-apps chart (requires ArgoCD installed):

    helm install sandbox-base sandbox-charts/sandbox-base

To uninstall the sandbox-base chart:

    helm delete sandbox-base