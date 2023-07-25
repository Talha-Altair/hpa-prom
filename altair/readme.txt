App:

image: talhaabdurrahman/ezio-prom
usage: /buy/a
       /view/a
       /metrics

k8s cluster

kind create cluster --name hehe --config kind-config.yaml

Install prometheus

helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
kubectl create ns monitoring
helm install prom-stack prometheus-community/kube-prometheus-stack -n monitoring

Install App

kubectl apply -f workload.yaml

Install servicemonitor

kubectl apply -f servicemonitor.yaml