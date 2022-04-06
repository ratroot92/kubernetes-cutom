Vagrant.configure("2") do |config|
    config.vm.define "master" do |master|
      master.vm.box_download_insecure = true    
      master.vm.box = "bento/ubuntu-20.04"        ## For ubuntu 18.04 use - hashicorp/bionic64
      master.vm.network "private_network", ip: "192.168.59.1"
      master.vm.hostname = "master"
      master.vm.provider "virtualbox" do |v|
        v.name = "master"
        v.memory = 2048
        v.cpus = 2
      end
    end
  
    config.vm.define "worker" do |worker|
      worker.vm.box_download_insecure = true 
      worker.vm.box = "bento/ubuntu-20.04"        ## For ubuntu 18.04 use - hashicorp/bionic64
      worker.vm.network "private_network", ip: "192.168.59.2"
      worker.vm.hostname = "worker"
      worker.vm.provider "virtualbox" do |v|
        v.name = "worker"
        v.memory = 1024
        v.cpus = 1
      end
    end
  
  end



# 192.168.59.1 master.burrency.com master 
# 192.168.59.2 workder.burrency.com worker


# kubectl is not healthy solve it via 
# https://stackoverflow.com/questions/52119985/kubeadm-init-shows-kubelet-isnt-running-or-healthy

### Running  
# sudo kubeadm init --apiserver-advertise-address=192.168.59.1 
###


# Your Kubernetes control-plane has initialized successfully!
# To start using your cluster, you need to run the following as a regular user:
#   mkdir -p $HOME/.kube
#   sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
#   sudo chown $(id -u):$(id -g) $HOME/.kube/config
# Alternatively, if you are the root user, you can run:
# export KUBECONFIG=/etc/kubernetes/admin.conf

# You should now deploy a pod network to the cluster.
# Run "kubectl apply -f [podnetwork].yaml" with one of the options listed at:
#   https://kubernetes.io/docs/concepts/cluster-administration/addons/

# Then you can join any number of worker nodes by running the following on each as root:

# sudo kubeadm join 192.168.59.1:6443 --token nzsd3t.23m4y171hoya8xfu --discovery-token-ca-cert-hash sha256:1f4ee012f73eb5c723609f2d3bba5330c216d3a7a0bbe6959007c9c5945e83c1 