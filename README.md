 C:\C#\K8s> kubectl get pod
No resources found in default namespace.
PS C:\C#\K8s> kubectl apply -f mongo-config.yaml
error: no objects passed to apply
PS C:\C#\K8s> kubectl apply -f mongo-config.yaml
configmap/mongo-config created
PS C:\C#\K8s> kubectl apply -f mongo-secret.yaml
secret/mongo-secret created
PS C:\C#\K8s> kubectl apply -f mongo.yaml
error: error parsing mongo.yaml: error converting YAML to JSON: yaml: line 23: did not find expected '-' indicator
PS C:\C#\K8s> kubectl apply -f mongo.yaml
deployment.apps/mongo-deployment created
service/mongo-service created
PS C:\C#\K8s> kubectl apply -f webapp.yaml
deployment.apps/webapp-deployment created
error: error parsing webapp.yaml: error converting YAML to JSON: yaml: line 7: mapping values are not allowed in this context      
PS C:\C#\K8s> kubectl apply -f webapp.yaml
deployment.apps/webapp-deployment unchanged
service/webapp-service created
PS C:\C#\K8s> 



PS C:\Users\user> kubectl get svc
NAME             TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE
kubernetes       ClusterIP   10.96.0.1       <none>        443/TCP          3h50m
mongo-service    ClusterIP   10.97.231.113   <none>        27017/TCP        8m35s
webapp-service   NodePort    10.104.244.33   <none>        3000:30100/TCP   7m24s
PS C:\Users\user> minikube ip
W0214 15:38:37.394664    2492 main.go:291] Unable to resolve the current Docker CLI context "default": context "default": context not found: open C:\Users\user\.docker\contexts\meta\37a8eec1ce19687d132fe29051dca629d164e2c4958ba141d5f4133a33f0688f\meta.json: The system cannot find the path specified.
192.168.49.2
PS C:\Users\user> kubectl get node
NAME       STATUS   ROLES           AGE     VERSION
minikube   Ready    control-plane   3h52m   v1.28.3
PS C:\Users\user> kubectl get node -o wide
NAME       STATUS   ROLES           AGE     VERSION   INTERNAL-IP    EXTERNAL-IP   OS-IMAGE             KERNEL-VERSION                       CONTAINER-RUNTIME
minikube   Ready    control-plane   3h52m   v1.28.3   192.168.49.2   <none>        Ubuntu 22.04.3 LTS   5.15.133.1-microsoft-standard-WSL2   docker://24.0.7
