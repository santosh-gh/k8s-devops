$GITHUB_TOKEN = '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'
$GITHUB_USER = 'santosh-gh'
$GITHUB_REPO = 'K8S-DEVOPS'

git auth login

flux bootstrap github --owner=$GITHUB_USER --repository=$GITHUB_REPO --branch=main --path=./clusters/my-cluster-cluster --personal

kubectl api-resources | grep flux

flux create source git podinfo --url=https://github.com/dexterposh/podinfo --branch=main --interval=30s --export > ./clusters/my-cluster/podinfo-source.yaml