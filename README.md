1. Install Docker and configure it, and run `swapoff -a`. See [Docker installation](https://kubernetes.io/docs/setup/production-environment/container-runtimes/#forwarding-ipv4-and-letting-iptables-see-bridged-traffic).

2. Clone the project.

3. Set the inventory.

4. Run it.

5. After installing, use the following command:

    ```bash
    mkdir -p $HOME/.kube
    sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
    sudo chown $(id -u):$(id -g) $HOME/.kube/config

    mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config
    ```

6. Source: [Ansible Galaxy - geerlingguy/kubernetes](https://galaxy.ansible.com/ui/standalone/roles/geerlingguy/kubernetes/install/)


7.Configuration containerd (config.toml)
Set the cgroup driver for runc to systemd
Set the cgroup driver for runc to systemd, which is required for the kubelet.
For more information on this config file see the containerd configuration docs here and also here.

At the end of this section in /etc/containerd/config.toml

      [plugins."io.containerd.grpc.v1.cri".containerd.runtimes.runc.options]
      ...
Change the value for SystemCgroup from false to true.

            SystemdCgroup = true
If you like, you can use sed to swap it out in the file without having to edit the file manually.

sudo sed -i 's/            SystemdCgroup = false/            SystemdCgroup = true/' /etc/containerd/config.toml
Restart containerd with the new configuration
sudo systemctl restart containerd
