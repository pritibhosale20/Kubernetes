# Automated Kubernetes Installation on Ubuntu Server

Step 1: Download the Installation Script on the Master Node

Run the following command on the master node to download the installation scripts:
```
wget https://raw.githubusercontent.com/pritibhosale20/Kubernetes/main/kubernetes_installation_onUbuntu/common.sh
wget https://raw.githubusercontent.com/pritibhosale20/Kubernetes/main/kubernetes_installation_onUbuntu/master.sh
```
Step 2: Download the Installation Script on Worker Nodes
Run this command on each worker node:
```
wget https://raw.githubusercontent.com/pritibhosale20/Kubernetes/main/kubernetes_installation_onUbuntu/common.sh
```
Step 3: Make the Scripts Executable

Grant execution permissions to the scripts on both master and worker nodes:
```
sudo chmod +x common.sh
```
On the master node, also make master.sh executable:
```
sudo chmod +x master.sh
```
Step 4: Run the Installation Scripts
On the Master Node:
```
./common.sh
./master.sh
```
On Worker Nodes:
```
./common.sh
```
Step 5: Join Worker Nodes to the Cluster

After the master node is set up, it will provide a kubeadm join command. Run this command on each worker node with sudo to join them to the cluster.

Step 6: Verify the Cluster Setup

On the master node, check the readiness of all nodes:
```
kubectl get nodes
```
This command should display the master and worker nodes in the Ready state.
