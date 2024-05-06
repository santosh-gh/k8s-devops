git auth login

flux bootstrap github --owner=$GITHUB_USER --repository=$GITHUB_REPO --branch=main --path=./clusters/my-cluster --personal

kubectl api-resources | grep flux

flux create source git k8s-devops --url=https://github.com/santosh-gh/k8s-devops --branch=main --interval=30s --export > ./clusters/my-cluster/helloapp-source.yaml

kubectl get gitrepositories.source.toolkit.fluxcd.io -n flux-system

flux get sources git

flux create kustomization k8s-devops --source=k8s-devops --path="./k8s" --prune=true --validation=client --interval=5m --export > ./clusters/my-cluster/helloapp-kustomization.yaml

kubectl get all -n flux-system

flux bootstrap github --owner=$GITHUB_USER --repository=$GITHUB_REPO --branch=main --path=./clusters/my-cluster --personal

flux get kustomization --watch

flux reconcile source git flux-system -n flux-system

flux create source git podinfo --url=https://github.com/dexterposh/podinfo --branch=main --interval=30s --export > ./clusters/my-cluster/podinfo-source.yaml

flux create kustomization podinfo --source=podinfo --path="./kustomize" --prune=true --validation=client --interval=5m --export > ./clusters/my-cluster/podinfo-kustomization.yaml

flux create source git mac-repo  --url=https://github.com/amit17133129/mac-repo  --branch=main --interval=30s --export > ./app-cluster/source.yaml

