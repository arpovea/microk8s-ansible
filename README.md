# Despliegue de Microk8s con Ansible

Con este playbook podrás porvisionar un cluster de microk8s ademas de un balanceo con HAProxy para balancear la api de kubernetes y las aplicaciones que quieras exponer en el cluster.

En la siguiente imagen se muestra un diagrama donde se ve la infraestructura final que se provisiona desde un bastión con ansible.

![Diagrama](img/microk8s_ansible.png)

Se recomiendan las siguientes MV:

- 3 Control Planes
- 2 Workers
- 1 Balance con HAProxy

> [!NOTE]
> Adicionalmente se necesitará una máquina desde la que lanzar ansible.

Cada rol de este playbook tiene su propio README que explica su funcionamiento y variables:
