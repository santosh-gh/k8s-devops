
    docker build -t web-api .
    docker images
    docker run -d -p 32766:8080 hello-app:latest
    docker ps

    docker build -t hello-app:v1 .
    docker tag hello-app:v1  e880613/hello-app:v1
    docker push e880613/hello-app:v1

    docker run -d -p 32766:8080 hello-app:v2


    http://localhost:32766/

    
    docker stop 79c669e62ff4
    docker rm 79c669e62ff4


    helm lint .\hello-app  
    helm template .\hello-app
    helm install helloapp --debug --dry-run  .\hello-app
    helm install helloapp  .\hello-app

# For cluster Ip
    kubectl port-forward [pod] 15687:8080
    kubectl port-forward helloapp-hello-app-6f5bd7b58-vtzzm 15687:8080

# For NodePort
    kubectl port-forward [service] --address 0.0.0.0 8080:8080 
    kubectl port-forward svc/helloapp-hello-app --address 0.0.0.0 8080:8080 

    helm upgrade  helloapp .\hello-app

    helm list -a

    helm delete helloapp