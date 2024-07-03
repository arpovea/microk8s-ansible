# Initial Setup

Este rol se encarga de realizar la instalación de la paqueteria y configuraciones iniciales para microk8s.

## Documentación de variables de Initial Setup

### Configuración de DNS

| Variable             | Descripción                                                                | Valor por defecto       |
|----------------------|----------------------------------------------------------------------------|-------------------------|
| `initial_setup_nameservers`        | Lista de servidores DNS principales.                                        | `10.10.10.3`, `8.8.8.8`    |
| `initial_setup_fallback_dns`       | Lista de servidores DNS de respaldo.                                        | `1.1.1.1`, `1.0.0.1`    |
| `initial_setup_resolved_conf_path` | Ruta al archivo de configuración de systemd-resolved.                       | `/etc/systemd/resolved.conf` |

### Configuración de NTP

| Variable        | Descripción                                                                    | Valor por defecto       |
|-----------------|--------------------------------------------------------------------------------|-------------------------|
| `initial_setup_ntp_servers`   | Lista de servidores NTP para sincronización de tiempo.                         | `ntp.ubuntu.com`        |

### Versión de MicroK8s

| Variable             | Descripción                                                                | Valor por defecto       |
|----------------------|----------------------------------------------------------------------------|-------------------------|
| `initial_setup_microk8s_version`   | Especifica la versión de MicroK8s a instalar.                              | `1.30/stable`           |

### Configuración de Networking de MicroK8s con Kube-OVN

| Variable              | Descripción                                                                | Valor por defecto       |
|-----------------------|----------------------------------------------------------------------------|-------------------------|
| `initial_setup_pod_network_cidr`    | Rango de IP para la red de pods.                                           | `10.16.0.0/16`          |
| `initial_setup_service_network_cidr`| Rango de IP para la red de servicios.                                      | `10.96.0.0/12`          |

### Configuración de IP y DNS adicionales para el API server

| Variable              | Descripción                                                                | Valor por defecto              |
|-----------------------|----------------------------------------------------------------------------|--------------------------------|
| `initial_setup_service_api_kubernetes`    | Especifica la IP del servicio de la API de Kubernetes.               | `10.96.0.1`                         |
| `initial_setup_load_balancer_ip`    | IP del balanceador de carga para incluir en el certificado del API server. | `10.10.10.16`                |
| `initial_setup_load_balancer_dns`   | DNS del balanceador de carga para incluir en el certificado del API server.| `api-microk8s.arpovea.com`     |