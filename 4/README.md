
kubectl create -f service.yml
kubectl create -f deploy.yml

kubectl get deploy hello

kubectl describe deploy hello

kubectl get rs

# rolling upgrade (change the container version)

kubectl apply -f deploy.yml --record

kubectl rollout status deployment hello

kubectl get deploy

kubectl get deploy hello

# rollback

# get history
kubectl rollout history deployment hello

# show replicaset upgrades (empty old rs)
kubectl get rs

kubectl rollout undo deployment hello --to-revision=1

# see one more than max because of maxSurge

kubectl get deploy hello

# status

kubectl rollout status deployment hello



