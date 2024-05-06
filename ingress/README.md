
# Deploy the nginx-ingress controller 
kubectl apply --filename https://raw.githubusercontent.com/kubernetes/ingress-nginx/master/deploy/static/provider/kind/deploy.yaml

# Wait for it to be ready by running
kubectl wait --namespace ingress-nginx --for=condition=ready pod --selector=app.kubernetes.io/component=controller --timeout=90s

kubectl apply -f helloworld-app1.yaml --namespace ingress-nginx
kubectl apply -f helloworld-app2.yaml --namespace ingress-nginx
kubectl apply -f helloworld-ingress.yaml --namespace ingress-nginx

curl localhost:1080/hello-world-one
curl localhost:1080/hello-world-two

http://localhost:1080/hello-world-one
http://localhost:1080/hello-world-two

kubectl delete -f helloworld-app1.yaml
kubectl delete -f helloworld-app2.yaml
kubectl delete -f helloworld-ingress.yam

