# Despliegue de Microk8s con Ansible

Con este playbook podrás provisionar un cluster de microk8s además de un balanceo con HAProxy para balancear la api de kubernetes y las aplicaciones que quieras exponer en el cluster. 

Adicionalmente se despliega ArgoCD y Tekton para poder trabajar con CI/CD.

Se realizan varios test sobre el cluster:

- [Sonobuoy](https://sonobuoy.io/)
- [Kube-bench](https://aquasecurity.github.io/kube-bench/v0.6.5/)

En la siguiente imagen se muestra un diagrama donde se ve la infraestructura final que se provisiona desde un bastión con ansible.

![Diagrama](img/microk8s_ansible.png)

Se recomiendan las siguientes MV:

- 3 Control Planes
- 2 Workers
- 1 Balance con HAProxy

> [!IMPORTANT]
> Adicionalmente se necesitará una máquina desde la que lanzar ansible.

Cada rol de este playbook tiene su propio README que explica su funcionamiento y variables:

- [Initial Setup](https://github.com/arpovea/microk8s-ansible/blob/main/roles/initial_setup/README.md)    
- [Microk8s Init](https://github.com/arpovea/microk8s-ansible/blob/main/roles/microk8s_init/README.md)
- [Microk8s Join](https://github.com/arpovea/microk8s-ansible/blob/main/roles/microk8s_join/README.md)
- [ArgoCD](https://github.com/arpovea/microk8s-ansible/blob/main/roles/argocd/README.md)
- [Tekton](https://github.com/arpovea/microk8s-ansible/blob/main/roles/tekton/README.md)
- [HAProxy](https://github.com/arpovea/microk8s-ansible/blob/main/roles/haproxy/README.md)
- [Test Sonoybuoy](https://github.com/arpovea/microk8s-ansible/blob/main/roles/sonobuoy/README.md)
- [Test Kube-bench](https://github.com/arpovea/microk8s-ansible/blob/main/roles/kube_bench/README.md)

> [!CAUTION]
> Este escenario se ha testeado con:
>
>- Ubuntu 22.04
>- Ansible: v2.17.1
>- Microk8s: v1.30/stable
