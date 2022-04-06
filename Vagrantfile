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
#  sudo kubeadm init --apiserver-advertise-address=192.168.59.1
# sudo kubeadm join 192.:6443 --token g2bsw7.5xr3bqc21eqyc6r7 --discovery-token-ca-cert-hash sha256:39b2b0608b9300b3342a8d0a0e9204c8fc74d45b008043a810f94e4f1fb8861f
#