# HAProxy

Este rol se encarga de la instalación y configuración de HAProxy.

## Documentación de Variables de HAPROXY

| Variable          | Descripción                                                                 | Valor por defecto  |
|-------------------|-----------------------------------------------------------------------------|--------------------|
| `enable_haproxy`  | Habilita o deshabilita la instalación de HAPROXY.                            | `true`             |
| `k8s_nodes`       | Lista de nodos Worker para HAPROXY con sus nombres e IPs correspondientes.   | Ver detalle abajo  |
| `k8s_control_plane` | Lista de nodos de Control Plane para HAPROXY con sus nombres e IPs correspondientes. | Ver detalle abajo  |

### Detalle de `k8s_nodes`

| Nombre           | IP             |
|------------------|----------------|
| `microk8s-master1` | `10.10.10.11` |
| `microk8s-master2` | `10.10.10.12` |
| `microk8s-master3` | `10.10.10.13` |
| `microk8s-worker1` | `10.10.10.14` |
| `microk8s-worker2` | `10.10.10.15` |

***Nota:*** Estos valores son usados para rellenar el template `haproxy.cfg.j2`

### Detalle de `k8s_control_plane`

| Nombre           | IP             |
|------------------|----------------|
| `microk8s-master1` | `10.10.10.11` |
| `microk8s-master2` | `10.10.10.12` |
| `microk8s-master3` | `10.10.10.13` |

***Nota:*** Estos valores son usados para rellenar el template `haproxy.cfg.j2`
