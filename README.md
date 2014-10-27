docker-mesos-cluster
====================

Playbook to setup a mesos cluster with docker enable on Centos 6

# Liste des ports à ouvrir pour les différents composants ( services )

Marathon : 8080
Mesos Master : 5050
Mesos Slave : 5051
Zookeeper : 2181, 2888, 3888
Nginx : 80


# Pour deployer la clé publique ssh avec ansible

ansible all -m yum -a "name=libselinux-python" --ask-pass --sudo --ask-sudo
ansible all -m authorized_key -a "user={{ user }} key=\"{{ lookup('file','~/.ssh/id_rsa.pub') }}\"" --ask-pass