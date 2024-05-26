https://particule.io/en/blog/flux-kustomize/

git add . && git commit -m "helm repo" && git push origin main

kubectl create ns pre
kubectl create ns prd

kubectl kustomize pre
kubectl kustomize prd

kubectl apply -k pre/  
kubectl apply -k prd/  

kubectl port-forward  pod/pre-helloworld-v1-66c455598c-pc9n8 8080:8080 -n pre 
kubectl port-forward service/pre-helloworld-v1 -n pre --address 0.0.0.0 8080:8080 

http://localhost:8080/
