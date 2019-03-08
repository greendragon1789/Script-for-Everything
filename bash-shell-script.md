# Command in Linux

- Script run for loop in order to delete pod
```
for k in $(kubectl get pods | grep be-mysql-cluster | awk '{print $1}'); \
do echo $k; \
sleep 2; \
kubectl delete pods $k; \
done
```
or
```
kubectl get job | awk '{print $1}' | xargs kubectl delete job
kubectl get job | grep cluster | awk '{print $1}' | xargs kubectl delete job
```
