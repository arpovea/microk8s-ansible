# HAProxy

Este rol se encarga de la instalación y configuración de HAProxy.

## Documentación de Variables de HAProxy

| Variable          | Descripción                                                                 | Valor por defecto  |
|-------------------|-----------------------------------------------------------------------------|--------------------|
| `haproxy_enable`  | Habilita o deshabilita la instalación de HAProxy.                            | `true`             |
| `haproxy_k8s_nodes`       | Lista de nodos Worker para HAProxy con sus nombres e IPs correspondientes.   | Ver detalle abajo  |
| `haproxy_k8s_control_plane` | Lista de nodos de Control Plane para HAProxy con sus nombres e IPs correspondientes. | Ver detalle abajo  |

### Detalle de `haproxy_k8s_nodes`

| Nombre           | IP             |
|------------------|----------------|
| `microk8s-master1` | `10.10.10.34` |
| `microk8s-master2` | `10.10.10.35` |
| `microk8s-master3` | `10.10.10.36` |
| `microk8s-worker1` | `10.10.10.37` |
| `microk8s-worker2` | `10.10.10.38` |

***Nota:*** Estos valores son usados para rellenar el template `haproxy.cfg.j2`

### Detalle de `haproxy_k8s_control_plane`

| Nombre           | IP             |
|------------------|----------------|
| `microk8s-master1` | `10.10.10.34` |
| `microk8s-master2` | `10.10.10.35` |
| `microk8s-master3` | `10.10.10.36` |

***Nota:*** Estos valores son usados para rellenar el template `haproxy.cfg.j2`
