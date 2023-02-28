# sandbox-apps

![Version: 0.0.11](https://img.shields.io/badge/Version-0.0.11-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.0](https://img.shields.io/badge/AppVersion-1.0-informational?style=flat-square)

Sandbox Apps Helm Installer - deploys a collection of ArgoCD apps with initial configuration.

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| clhain | <clhain@gmail.com> |  |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| adminPass | string | `""` |  |
| apps.argo-virtual-server.destination.namespace | string | `"argocd"` |  |
| apps.argo-virtual-server.enabled | bool | `true` |  |
| apps.argo-virtual-server.source.helm.params.clusterDomain | string | `"{{ .Values.clusterDomain }}"` |  |
| apps.argo-virtual-server.source.helm.params.clusterTLSInsecure | string | `"{{ .Values.clusterTLSInsecure }}"` |  |
| apps.argo-virtual-server.source.path | string | `"services/argo-virtual-server"` |  |
| apps.argo-virtual-server.syncWave | string | `"5"` |  |
| apps.cert-manager.destination.namespace | string | `"cert-manager"` |  |
| apps.cert-manager.enabled | bool | `true` |  |
| apps.cert-manager.source.helm.params."letsEncryptIssuer.contactEmail" | string | `"{{ .Values.letsEncryptContactEmail }}"` |  |
| apps.cert-manager.source.helm.params.clusterTLSInsecure | string | `"{{ .Values.clusterTLSInsecure }}"` |  |
| apps.cert-manager.source.path | string | `"services/cert-manager"` |  |
| apps.cert-manager.syncWave | string | `"1"` |  |
| apps.gatekeeper.destination.namespace | string | `"gatekeeper"` |  |
| apps.gatekeeper.enabled | bool | `true` |  |
| apps.gatekeeper.source.path | string | `"services/gatekeeper"` |  |
| apps.gatekeeper.syncWave | string | `"2"` |  |
| apps.grafana.destination.namespace | string | `"grafana"` |  |
| apps.grafana.enabled | bool | `true` |  |
| apps.grafana.source.helm.params.clusterDomain | string | `"{{ .Values.clusterDomain }}"` |  |
| apps.grafana.source.helm.params.clusterTLSInsecure | string | `"{{ .Values.clusterTLSInsecure }}"` |  |
| apps.grafana.source.path | string | `"services/grafana"` |  |
| apps.grafana.syncWave | string | `"6"` |  |
| apps.loki.destination.namespace | string | `"loki"` |  |
| apps.loki.enabled | bool | `true` |  |
| apps.loki.extraFields | string | `"ignoreDifferences:\n- group: apps\n  kind: StatefulSet\n  jsonPointers:\n  - /spec/persistentVolumeClaimRetentionPolicy\n"` |  |
| apps.loki.source.path | string | `"services/loki"` |  |
| apps.loki.syncWave | string | `"5"` |  |
| apps.nginx-ingress.destination.namespace | string | `"nginx-ingress"` |  |
| apps.nginx-ingress.enabled | bool | `true` |  |
| apps.nginx-ingress.source.helm.params."nginx-ingress.controller.service.annoations.cloud\.google\.com/load-balancer-type" | string | `"External"` |  |
| apps.nginx-ingress.source.helm.params."nginx-ingress.controller.service.create" | string | `"{{ not (eq .Values.clusterIngressIP \"\") }}"` |  |
| apps.nginx-ingress.source.helm.params."nginx-ingress.controller.service.loadBalancerIP" | string | `"{{ .Values.clusterIngressIP }}"` |  |
| apps.nginx-ingress.source.path | string | `"services/nginx-ingress"` |  |
| apps.nginx-ingress.syncWave | string | `"4"` |  |
| apps.nginx-mesh.destination.namespace | string | `"nginx-mesh"` |  |
| apps.nginx-mesh.enabled | bool | `true` |  |
| apps.nginx-mesh.source.path | string | `"services/nginx-mesh"` |  |
| apps.nginx-mesh.syncWave | string | `"3"` |  |
| apps.oauth-proxy.destination.namespace | string | `"oauth-proxy"` |  |
| apps.oauth-proxy.enabled | bool | `true` |  |
| apps.oauth-proxy.source.helm.params.clusterDomain | string | `"{{ .Values.clusterDomain }}"` |  |
| apps.oauth-proxy.source.helm.params.clusterLocalAuth | string | `"{{ .Values.clusterLocalAuth }}"` |  |
| apps.oauth-proxy.source.helm.params.clusterTLSInsecure | string | `"{{ .Values.clusterTLSInsecure }}"` |  |
| apps.oauth-proxy.source.helm.params.oidcIssuerURL | string | `"{{ .Values.oidcIssuerURL }}"` |  |
| apps.oauth-proxy.source.helm.params.oidcPermittedEmailDomains | string | `"{{ .Values.oidcPermittedEmailDomains }}"` |  |
| apps.oauth-proxy.source.path | string | `"services/oauth-proxy"` |  |
| apps.oauth-proxy.syncWave | string | `"5"` |  |
| apps.opentelemetry-operator.destination.namespace | string | `"opentelemetry-operator"` |  |
| apps.opentelemetry-operator.enabled | bool | `true` |  |
| apps.opentelemetry-operator.source.path | string | `"services/opentelemetry-operator"` |  |
| apps.opentelemetry-operator.syncWave | string | `"2"` |  |
| apps.prometheus-operator-crds.destination.namespace | string | `"prometheus-operator"` |  |
| apps.prometheus-operator-crds.enabled | bool | `true` |  |
| apps.prometheus-operator-crds.source.extraSourceFields | string | `"directory:\n  recurse: true\n"` |  |
| apps.prometheus-operator-crds.source.path | string | `"charts/kube-prometheus-stack/crds/"` |  |
| apps.prometheus-operator-crds.source.repoURL | string | `"https://github.com/prometheus-community/helm-charts.git"` |  |
| apps.prometheus-operator-crds.source.targetRevision | string | `"kube-prometheus-stack-45.4.0"` |  |
| apps.prometheus-operator-crds.syncOptions[0] | string | `"CreateNamespace=true"` |  |
| apps.prometheus-operator-crds.syncOptions[1] | string | `"Replace=true"` |  |
| apps.prometheus-operator-crds.syncWave | string | `"1"` |  |
| apps.prometheus-operator.destination.namespace | string | `"prometheus-operator"` |  |
| apps.prometheus-operator.enabled | bool | `true` |  |
| apps.prometheus-operator.source.extraSourceFields | string | `"helm:\n  skipCrds: true\n"` |  |
| apps.prometheus-operator.source.path | string | `"services/prometheus-operator"` |  |
| apps.prometheus-operator.syncWave | string | `"2"` |  |
| apps.sealed-secrets.destination.namespace | string | `"sealed-secrets"` |  |
| apps.sealed-secrets.enabled | bool | `true` |  |
| apps.sealed-secrets.source.path | string | `"services/sealed-secrets"` |  |
| apps.sealed-secrets.syncWave | string | `"2"` |  |
| apps.tempo.destination.namespace | string | `"tempo"` |  |
| apps.tempo.enabled | bool | `true` |  |
| apps.tempo.source.path | string | `"services/tempo"` |  |
| apps.tempo.syncWave | string | `"5"` |  |
| authSecretName | string | `"oauth-secret"` |  |
| authSecretNamespace | string | `"argocd"` |  |
| clusterDomain | string | `"localtest.me"` |  |
| clusterIngressIP | string | `nil` |  |
| clusterLocalAuth | bool | `true` |  |
| clusterTLSInsecure | bool | `false` |  |
| cookieSecret | string | `""` |  |
| default.app.autoSyncPrune | bool | `true` |  |
| default.app.destination.namespace | string | `nil` |  |
| default.app.destination.server | string | `"https://kubernetes.default.svc"` |  |
| default.app.enableAutoSync | bool | `true` |  |
| default.app.extraFields | string | `"ignoreDifferences:\n- group: apiextensions.k8s.io\n  kind: CustomResourceDefinition\n  jsonPointers:\n  - /metadata/annotations\n"` |  |
| default.app.project | string | `"cluster-services"` |  |
| default.app.selfHeal | bool | `true` |  |
| default.app.source.path | string | `nil` |  |
| default.app.source.repoURL | string | `"https://github.com/clhain/sandbox.git"` |  |
| default.app.source.targetRevision | string | `"HEAD"` |  |
| default.app.syncOptions[0] | string | `"CreateNamespace=true"` |  |
| default.app.syncWave | string | `"10"` |  |
| deployArgoProject | bool | `true` |  |
| enableVirtualServer | bool | `true` |  |
| letsEncryptContactEmail | string | `nil` |  |
| oauthProxyNamespace | string | `"oauth-proxy"` |  |
| oauthProxySecretEnable | bool | `true` |  |
| oidcClientID | string | `""` |  |
| oidcClientSecret | string | `""` |  |
| oidcIssuerURL | string | `""` |  |
| oidcPermittedEmailDomains | string | `"*"` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.8.1](https://github.com/norwoodj/helm-docs/releases/v1.8.1)
