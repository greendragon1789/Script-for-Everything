# Command in Linux

- Script run for loop in order to delete pod
```
for k in $(kgp | grep be-mysql-cluster | awk '{print $1}'); do echo $k; sleep 2; kubectl delete pod $k;done
```
