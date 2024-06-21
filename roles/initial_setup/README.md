# Initial Setup

Este rol se encarga de realizar la instalación de la paqueteria y configuraciones iniciales para microk8s.

## Documentación de variables de Initial Setup

### Configuración de DNS

| Variable             | Descripción                                                                | Valor por defecto       |
|----------------------|----------------------------------------------------------------------------|-------------------------|
| `nameservers`        | Lista de servidores DNS principales.                                        | `8.8.8.8`, `8.8.4.4`    |
| `fallback_dns`       | Lista de servidores DNS de respaldo.                                        | `1.1.1.1`, `1.0.0.1`    |
| `resolved_conf_path` | Ruta al archivo de configuración de systemd-resolved.                       | `/etc/systemd/resolved.conf` |

### Configuración de NTP

| Variable        | Descripción                                                                    | Valor por defecto       |
|-----------------|--------------------------------------------------------------------------------|-------------------------|
| `ntp_servers`   | Lista de servidores NTP para sincronización de tiempo.                         | `ntp.ubuntu.com`        |

### Versión de MicroK8s

| Variable             | Descripción                                                                | Valor por defecto       |
|----------------------|----------------------------------------------------------------------------|-------------------------|
| `microk8s_version`   | Especifica la versión de MicroK8s a instalar.                              | `1.30/stable`           |

### Configuración de Networking de MicroK8s con Kube-OVN

| Variable              | Descripción                                                                | Valor por defecto       |
|-----------------------|----------------------------------------------------------------------------|-------------------------|
| `enable_kube_ovn`     | Habilita o deshabilita la configuración de Kube-OVN.                       | `true`                  |
| `pod_network_cidr`    | Rango de IP para la red de pods.                                           | `10.16.0.0/16`          |
| `service_network_cidr`| Rango de IP para la red de servicios.                                      | `10.96.0.0/12`          |
| `dns_ip`              | Dirección IP del servidor DNS dentro del clúster.                          | `10.96.0.10`            |

### Configuración de IP y DNS adicionales para el API server

| Variable              | Descripción                                                                | Valor por defecto              |
|-----------------------|----------------------------------------------------------------------------|--------------------------------|
| `load_balancer_ip`    | IP del balanceador de carga para incluir en el certificado del API server. | `192.168.1.100`                |
| `load_balancer_dns`   | DNS del balanceador de carga para incluir en el certificado del API server.| `api-microk8s.arpovea.com`     |