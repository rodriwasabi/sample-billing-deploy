# Prometheus
#kb: https://kumar-allamraju.medium.com/azure-kubernetes-monitoring-aks-with-prometheus-e2105db6dd16

# helm repo
helm repo add stable https://charts.helm.sh/stable

kubectl create ns monitoring

helm install prometheus stable/prometheus-operator --namespace monitoring

kubectl --namespace monitoring get pods -l "release=prometheus"

# Access:
http://monitoring.coconut-cloud.tk/

# To get creds:
kubectl get secret -n monitoring prometheus-grafana -o yaml

echo <user>|base64 -D
echo <oassword>|base64 -D