https://particule.io/en/blog/flux-kustomize/


kubectl create ns preprod
kubectl create ns prod

kubectl kustomize preprod
kubectl kustomize prod

kubectl apply -k preprod/  
kubectl apply -k prod/  