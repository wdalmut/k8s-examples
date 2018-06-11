
kubectl create -f pod.yml

kubectl get pods

kubectl get pods -o json hello

kubectl describe pods hello

kubectl exec hello ps aux

kubectl exec -it hello sh # then curl localhost:80
