1.Install Docker and Config it and swapoff -a    https://kubernetes.io/docs/setup/production-environment/container-runtimes/#forwarding-ipv4-and-letting-iptables-see-bridged-traffic  \n
2.clone the project \n
3.set inventory
4.run it.
5.after installing 
use this command

mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config


6.SRC:
https://galaxy.ansible.com/ui/standalone/roles/geerlingguy/kubernetes/install/
