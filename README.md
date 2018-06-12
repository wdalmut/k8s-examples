
https://labs.play-with-k8s.com

kubeadm init --apiserver-advertise-address $(hostname -i)

kubectl get nodes

kubectl apply -n kube-system -f \
"https://cloud.weave.works/k8s/net?k8s-version=$(kubectl version | base64 | tr -d '\n')"

kubectl get nodes

kubeadm join --token [kube init token]

kubectl get nodes
