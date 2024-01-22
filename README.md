1. Install Docker and configure it, and run `swapoff -a`. See [Docker installation](https://kubernetes.io/docs/setup/production-environment/container-runtimes/#forwarding-ipv4-and-letting-iptables-see-bridged-traffic).

2. Clone the project.

3. Set the inventory.

4. Run it.

5. After installing, use the following command:

    ```bash
    mkdir -p $HOME/.kube
    sudo cp -i /etc/kubernetes/admin.conf $(id -u):$(id -g) $HOME/.kube/config
    ```

6. Source: [Ansible Galaxy - geerlingguy/kubernetes](https://galaxy.ansible.com/ui/standalone/roles/geerlingguy/kubernetes/install/)
