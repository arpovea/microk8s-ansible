# Microk8s INIT

Este rol habilita complementos en el cluster (los que se comparten de forma horizontal) y genera el token para agregar los nodos.

## Documentación de variables

### Configuración de MetalLB e Ingress Controller

| Variable                | Descripción                                                                                   | Valor por defecto           |
|-------------------------|-----------------------------------------------------------------------------------------------|-----------------------------|
| `microk8s_init_metallb_ip_range`      | Rango de direcciones IP que MetalLB utilizará para asignar IPs a los servicios de tipo LoadBalancer. | `10.10.10.150-10.10.10.160` |
| `microk8s_init_ip_ingress_controller` | Dirección IP asignada al Ingress Controller utilizando el tipo de servicio LoadBalancer.       | `10.10.10.151`              |

### Instalación de addons horizontales

| Variable                | Descripción                                                                                   | Valor por defecto           |
|-------------------------|-----------------------------------------------------------------------------------------------|-----------------------------|
| `microk8s_init_addons.rbac`           | Habilita o deshabilita Role-Based Access Control (RBAC).                                       | `true`                      |
| `microk8s_init_addons.metallb`        | Habilita o deshabilita el complemento MetalLB para proporcionar soporte de balanceo de carga.  | `false`                     |
| `microk8s_init_addons.ingress`        | Habilita o deshabilita el complemento Ingress para gestionar el tráfico HTTP/HTTPS hacia los servicios. | `true`                      |
| `microk8s_init_addons.metrics_server` | Habilita o deshabilita el complemento Metrics Server para recopilar métricas del clúster.      | `true`                      |
| `microk8s_init_addons.dashboard`      | Habilita o deshabilita el complemento Kubernetes Dashboard para proporcionar una interfaz gráfica de usuario. | `true`                      |
| `microk8s_init_addons.storage`        | Habilita o deshabilita el complemento de almacenamiento.                                       | `false`                     |
| `microk8s_init_addons.registry`       | Habilita o deshabilita el complemento de registro de contenedores.                             | `false`                     |
