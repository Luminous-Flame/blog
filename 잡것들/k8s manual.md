```bash
helm install --namespace "graylog" graylog --set graylog.replicas=3 kongz/graylog

helm install --namespace "graylog" graylog -f values.yaml kongz/graylog

helm uninstall graylog -n graylog
```

```
helm repo add kongz https://charts.kong-z.com
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo add mongodb https://github.com/bitnami/charts/tree/master/bitnami/mongodb
```

kubectl create namespace graylog

helm resource 삭제 
kubectl delete svc,deploy,pod -l app=graylog -n graylog

```
helm install --namespace "graylog" graylog kongz/graylog \
--set storageClassName=local-storage \
--set tags.install-mongodb=false \
--set tags.install-opensearch=false \
--set graylog.mongodb.uri=mongodb://mongodb-mongodb-replicaset-0.mongodb-mongodb-replicaset.graylog.svc.cluster.local:27017/graylog?replicaSet=rs0 \ 
--set graylog.opensearch.hosts=http://opensearch-cluster-master-headless.graylog.svc.cluster.local:9200 \ 
--set graylog.opensearch.version=7
```

storage class 생성
kubectl apply -f storage_class.yaml
kubectl apply -f storage_pv.yaml
kubectl apply -f storage_pvc.yaml


storage class 제거
kubectl delete storageclass local-storage
kubectl delete pvc data-pvc
kubectl delete pv data-pv

storage class 확인
kubectl get pv
kubectl get pvc
kubectl get storageclasses

kubectl describe pvc data-pvc
kubectl describe pv data-pv

