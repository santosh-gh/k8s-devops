git auth login

flux bootstrap github --owner=$GITHUB_USER --repository=$GITHUB_REPO --branch=main --path=./clusters/my-cluster --personal

kubectl api-resources | grep flux

flux create source git k8s-devops --url=https://github.com/santosh-gh/k8s-devops --branch=main --interval=30s --export > ./clusters/my-cluster/helloapp-source.yaml

kubectl get gitrepositories.source.toolkit.fluxcd.io -n flux-system

flux get sources git

flux create kustomization k8s-devops --source=k8s-devops --path="./kustomize" --prune=true --validation=client --interval=5m --export > ./clusters/my-cluster/helloapp-kustomization.yaml