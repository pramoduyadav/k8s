# k8s
Kubernetes


sudo kubeadm join --token 118c3e.83b49999dc5dc034 \
10.128.0.3:6443 --discovery-token-ca-cert-hash \
sha256:40aa946e3f53e38271bae24723866f56c86d77efb49aedeb8a70cc189bfe2e1d

kubectl cluster-info


kubectl get node
kubectl --help
kubectl taint --help

kubectl describe nodes | grep -i taint
kubectl taint nodes --all node-role.kubernetes.io/master-
kubectl describe nodes | grep -i taint

kubectl get nodes

kubectl api-resources



kubectl create -f basic.yaml    --- creates pod
kubectl get pod
kubectl delete pod basicpod
kubectl get pod -o wide         -- -o wide option to see the internal IP assigned to the pod
kubectl logs <podname>


kubectl create -f basicservice.yaml   -- creates service which exposes the pod to other nodes and pods in cluster
kubectl get svc
kubectl delete svc basicservice

-- create a Deployment which gives us scalability, reliability, and updates.
kubectl create deployment firstpod --image=nginx
kubectl get deployment,pod
kubectl describe deployment firstpod
kubectl describe pod firstpod-6bb4574d94-rqk76

kubectl get namespaces
kubectl get pod -n kube-system
kubectl get pod --all-namespaces

kubectl get deploy,rs,po,svc,ep      --  rs for ReplicaSet, po for Pod, svc for Service, and ep for endpoint.
kubectl delete deployment firstpod

kubectl create deployment try1 --image=$repo/simpleapp
kubectl scale deployment try1 --replicas=6

#Run the bash shell interactively and touch the /tmp/healthy file.
kubectl exec -it try1-9869bdb88-rtchc -- /bin/bash

kubectl describe pod try1-76cc5ffcc6-tx4dz | tail
============

Chapter 4

#Delete pod using label
kubectl delete -l app=orange pod



