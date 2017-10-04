
http://www.dasblinkenlichten.com/getting-started-kubernetes-using-ansible/
http://www.dasblinkenlichten.com/getting-started-with-calico-on-kubernetes/

https://github.com/jonlangemak/ansible_kubernetes/issues/6

sudo apt-add-repository -y ppa:ansible/ansible
sudo apt-get update
sudo apt-get -y install ansible python-pip


sudo mv /etc/ansible/hosts /etc/ansible/hosts.orig

create /etc/ansible/hosts file with this content:
# This is the default ansible 'hosts' file.
#
# It should live in /etc/ansible/hosts
#
#   - Comments begin with the '#' character
#   - Blank lines are ignored
#   - Groups of hosts are delimited by [header] elements
#   - You can enter hostnames or ip addresses
#   - A hostname/ip can be a member of multiple groups

[masters]
ubuntu-1

[minions]
ubuntu-2
ubuntu-3
ubuntu-4
ubuntu-5



sudo mkdir -p /etc/ansible/roles/kubernetes
sudo cp -R /vagrant/files/ /etc/ansible/roles/kubernetes/
sudo cp -R /vagrant/handlers/ /etc/ansible/roles/kubernetes/
sudo cp -R /vagrant/tasks/ /etc/ansible/roles/kubernetes/
sudo cp -R /vagrant/vars/ /etc/ansible/roles/kubernetes/


VBoxManage list natnetworks

VBoxManage natnetwork stop --netname NatNetwork
VBoxManage natnetwork start --netname NatNetwork
VBoxManage list dhcpservers
