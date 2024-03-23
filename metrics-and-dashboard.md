## Steps


Step 1. `helm repo add kyverno https://kyverno.github.io/kyverno/`

Step 2. `helm repo update`

Step 3. `helm install kyverno kyverno/kyverno -n kyverno --create-namespace`

Step 4. `curl -s "https://raw.githubusercontent.com/kubernetes-sigs/kustomize/master/hack/install_kustomize.sh"  | bash`

Step 5. `kustomize build https://github.com/kyverno/policies/pod-security | kubectl apply -f `

Step 6. 


