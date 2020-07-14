# istio
Istio hands-on

We can run these in katacoda where env is readily available

Steps:

1. Create config map with command:

kubectl create configmap sidecar-config --from-file=envoy-config=envoy.yaml

2. Create deployment and service with command:

kubectl create -f deployment.yaml
kubectl create -f service.yaml

3. View istio-init logs

kubectl logs <podid> -c istio-init

4. View envoy logs

kubectl exec -it <podid> -c envoy sh
  
5. Check service with curl

kubectl get svc (get cluster ip)

curl <clusterip> - output printed
curl <clusterip>:8083 - Blackhole cluster should be hit.
