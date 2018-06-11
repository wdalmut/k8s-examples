
kubectl create -f replica.yml

kubectl create -f service.yml

kubectl get svc hello-svc

kubectl describe svc hello-svc

# endpoint

kubectl get ep hello-svc

kubectl describe ep hello-svc

# possible new deploy with new label with versioning and drop the old one manually or rollback
