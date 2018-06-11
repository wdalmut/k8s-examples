
kubectl create -f replica.yml

kubectl get rs

kubectl get rs/web-rs

kubectl get pods --show-labels

kubectl get rs web-rs --output=yaml

kubectl delete rs/web-rs --cascade=false

kubectl get rs

kubectl get pods --show-labels

kubectl create -f replica.yml

kubectl get rs/web-rs

# change replicas

kubectl apply -f replica.yml

kubectl get rs/web-rs


