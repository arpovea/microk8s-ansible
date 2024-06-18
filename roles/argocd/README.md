# Despliegue de ArgoCD

Este rol se encarga del despliegue de ArgoCD en Microk8s.

## Documentación de variables de ArgoCD

| Variable        | Descripción                                                    | Valor por defecto       |
|-----------------|----------------------------------------------------------------|-------------------------|
| `enable_argocd` | Habilita o deshabilita el despliegue de ArgoCD.               | `false`                 |
| `argocd_host`   | Hostname para acceder a ArgoCD.                                | `argocd.example.com`    |
