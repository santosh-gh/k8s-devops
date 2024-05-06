
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