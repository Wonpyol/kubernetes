# kubernetes
개발환경: MacOS Monterey 12.6
툴버젼
vagrant v2.2.9
oracle virtualbox 6.1.42
아이피변경
Vagrantfile:      cfg.vm.network "private_network", ip: "192.168.56.10"
Vagrantfile:      cfg.vm.network "private_network", ip: "192.168.56.10#{i}"
k8s_env_build.sh:echo "192.168.56.10 m-k8s" >> /etc/hosts
k8s_env_build.sh:for (( i=1; i<=$1; i++  )); do echo "192.168.56.10$i w$i-k8s" >> /etc/hosts; done
master_node.sh:--pod-network-cidr=172.16.0.0/16 --apiserver-advertise-address=192.168.56.10 \
work_nodes.sh:             --discovery-token-unsafe-skip-ca-verification 192.168.56.10:6443 \

