## Steps

## First install Kyverno in cluster

Step 1. `helm repo add kyverno https://kyverno.github.io/kyverno/`

Step 2. `helm repo update`

Step 3. `helm install kyverno kyverno/kyverno -n kyverno --create-namespace`

Step 4. `curl -s "https://raw.githubusercontent.com/kubernetes-sigs/kustomize/master/hack/install_kustomize.sh"  | bash`

// there is no progress bar so just give it some time, it will install.

Step 5. `./kustomize build https://github.com/kyverno/policies/pod-security | kubectl apply -f -`

// 

Step 6. 


## For setting up Kyverno Dashboard:

Step 1. `kubectl create namespace kyverno`

Step 2. 
```
helm install kyverno kyverno/kyverno \
--namespace kyverno \
--create-namespace \
--set metricsService.type=NodePort \
--set metricsService.nodePort=30539
```


Step 3. `kubectl apply -k github.com/kyverno/grafana-dashboard/examples/prometheus`

Step 4. `minikube ip`

Step 5. `minikube service prometheus-server -n kyverno`

Step 6. Then continue using Nirmata docs

## For setting Promethues in the github codespace

Step 1. `make kind-create-cluster`

Step 2. `make kind-deploy-kyverno`

Step 3. `kubectl apply -k github.com/kyverno/grafana-dashboard/examples/prometheus`

Step 4. `kubectl patch -n kyverno service kyverno-svc-metrics -p '{"spec":{"type":"NodePort","ports":[{"port":8000,"nodePort
":30539}]}}'   

for exposing the kyverno-svc-metrics

Step 5. `kubectl port-forward service/prometheus-server -n kyverno 9090:9090`

And you will have your promethues server running at localhost:9090
