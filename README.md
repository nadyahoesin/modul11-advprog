## Reflection on Hello Minikube

1. After I exposed the application as a service, everytime I open the application, the log shows every GET HTTP requests made.

2. The -n flag is used to specify the namespace of the requested objects. In this case, we use the command `kubectl get pods,services -n kube-system` to get the pods and services with the namespace `kube-system`, which is used for objects created by the Kubernetes system. We use that command to check whether the pods and services associated with `metrics-server` that is created by the Kubernetes system have been created or not. The output did not list the pods/services that I explicitly created because they have the namespace `default`, not `kube-system`.