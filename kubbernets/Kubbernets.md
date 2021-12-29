+ # Команди які необхідні при старті роботи з "Кубіком"

1. kubectl get pods -o wide - команда для виводу списку PODs з розширеними параметрами

```
kubectl get pods -o wide
```
```

NAME                              READY   STATUS    RESTARTS        AGE     IP           NODE       NOMINATED NODE   READINESS GATES
hello-minikube-6ddfcc9757-4h5d8   1/1     Running   1 (3h16m ago)   25h     172.17.0.5   minikube   <none>           <none>
nginx                             1/1     Running   0               3h15m   172.17.0.6   minikube   <none>           <none>
```

2. kubectl get pods - команда для виводу списку PODs 
```
kubectl get pods 
```
```
NAME                              READY   STATUS    RESTARTS        AGE
hello-minikube-6ddfcc9757-4h5d8   1/1     Running   1 (4h22m ago)   26h
nginx                             1/1     Running   0               4h22m
```
3. kubectl describe pods nginx - команда для опису певного PODa
```
Name:         nginx
Namespace:    default
Priority:     0
Node:         minikube/192.168.59.100
Start Time:   Tue, 28 Dec 2021 20:18:22 +0200
Labels:       run=nginx
Annotations:  <none>
Status:       Running
IP:           172.17.0.7
IPs:
  IP:  172.17.0.7
Containers:
  nginx:
    Container ID:   docker://30086362f6a4d1e51b95dc7fb0d6cb414476857bc242dd03eaeb61ac34937ba6
    Image:          nginx
    Image ID:       docker-pullable://nginx@sha256:366e9f1ddebdb844044c2fafd13b75271a9f620819370f8971220c2b330a9254
    Port:           <none>
    Host Port:      <none>
    State:          Running
      Started:      Tue, 28 Dec 2021 20:18:26 +0200
    Ready:          True
    Restart Count:  0
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-nxph4 (ro)
Conditions:
  Type              Status
  Initialized       True 
  Ready             True 
  ContainersReady   True 
  PodScheduled      True 
Volumes:
  kube-api-access-nxph4:
    Type:                    Projected (a volume that contains injected data from multiple sources)
    TokenExpirationSeconds:  3607
    ConfigMapName:           kube-root-ca.crt
    ConfigMapOptional:       <nil>
    DownwardAPI:             true
QoS Class:                   BestEffort
Node-Selectors:              <none>
Tolerations:                 node.kubernetes.io/not-ready:NoExecute op=Exists for 300s
                             node.kubernetes.io/unreachable:NoExecute op=Exists for 300s
Events:
  Type    Reason     Age   From               Message
  ----    ------     ----  ----               -------
  Normal  Scheduled  28s   default-scheduler  Successfully assigned default/nginx to minikube
  Normal  Pulling    27s   kubelet            Pulling image "nginx"
  Normal  Pulled     24s   kubelet            Successfully pulled image "nginx" in 3.210992925s
  Normal  Created    24s   kubelet            Created container nginx
  Normal  Started    24s   kubelet            Started container nginx
```
4. kubectl run  pods nginx --image nginx - cтворення POD з образу(image) nginx і надання імені nginx
```
kubectl run  pods nginx --image nginx
pod/pods created
```
5. kubectl delete pods nginx - виделення POD 
```
kubectl delete pods nginx
pod "nginx" deleted
```
