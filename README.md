# learn-argocd
Learn Argo CD

kubectl create namespace argocd-demo

ArgoCD Tutorial for Beginners | GitOps CD for Kubernetes
https://www.youtube.com/watch?v=MeU5_k9ssrs

```sh
k get all -n argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

k port-forward -n argocd service/argocd-server 18881:443

k -n argocd get secret argocd-initial-admin-secret

k apply -f application.yaml

k get all -n argocd-demo
NAME                        READY   STATUS              RESTARTS   AGE
pod/nginx-776f6d578-r7sqk   0/1     ContainerCreating   0          13s
pod/nginx-776f6d578-w6q46   0/1     ContainerCreating   0          13s

NAME                    TYPE        CLUSTER-IP    EXTERNAL-IP   PORT(S)    AGE
service/nginx-service   ClusterIP   10.96.92.96   <none>        8080/TCP   15s

NAME                    READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/nginx   0/2     2            0           24s

NAME                              DESIRED   CURRENT   READY   AGE
replicaset.apps/nginx-776f6d578   2         2         0       24s
```

---

## v2 for httpd server

```sh
docker pull httpd:2.4-alpine3.17
```