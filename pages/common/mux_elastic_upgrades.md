- Elastic upgrade Runbook
```
styri print --diff run/virgo/clusters/staging/aws-us-east-1-dos1.sy --match=es_\|kibana
kubectl get pods | grep elasticsearch
kubectl get pods | grep kibana
kubectl exec -it elasticsearch-0 bash
curl -s http://elasticsearch:9200/_cluster/health?pretty
curl -s 'localhost:9200/_cat/allocation?v'
styri update run/virgo/clusters/staging/aws-us-east-1-dos1.sy --match=es_\|kibana
kubectl delete pod -l app=elasticsearch
kubectl get pods | grep elasticsearch
kubectl exec -it elasticsearch-0 bash
curl -s http://elasticsearch:9200/_cluster/health?pretty
curl -s 'localhost:9200/_cat/allocation?v'
```
