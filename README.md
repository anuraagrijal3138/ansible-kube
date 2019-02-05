Steps to produce:
1. Create virtual boxes with Ubuntu 16.04.
2. Clone the repository to the master node.

REQUIREMENTS for virtual machines:
1. The virtual machines should have at least 1GB ram.
2. Install ansible in the master nodel.
3. These virtual machichines should have full connectivity and should bce able to ssh into one another without password.

Other requirements:
1. Change the hosts file to suite your setup.
2. Creating a Non-Root User on All Remote Servers:
   ansible-playbook -i hosts ~/kube-cluster/initial.yml
3. Install kuberntes' depndencies.
   ansible-playbook -i hosts ~/kube-cluster/kube-dependencies.yml
4. Setup the master node.
   ansible-playbook -i hosts ~/kube-cluster/master.yml
5. Setup the worker nodes.
   ansible-playbook -i hosts ~/kube-cluster/workers.yml
6. Verify the cluster is running by running "kubectl get nodes" in the master node.
7. Add other application with kubectl apply command to suit your requirements.
