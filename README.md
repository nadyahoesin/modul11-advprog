## Reflection on Hello Minikube

1. After I exposed the application as a service, everytime I open the application, the log shows every GET HTTP requests made.

2. The -n flag is used to specify the namespace of the requested objects. In this case, we use the command `kubectl get pods,services -n kube-system` to get the pods and services with the namespace `kube-system`, which is used for objects created by the Kubernetes system. We use that command to check whether the pods and services associated with `metrics-server` that is created by the Kubernetes system have been created or not. The output did not list the pods/services that I explicitly created because they have the namespace `default`, not `kube-system`.

## Reflection on Rolling Update & Kubernetes Manifest File

1. Rolling update deployment strategy is done by incrementally replacing the current pods with new ones, which allow the application to still be accessible. This strategy allows the application to be updated without downtime. Recreate deployment strategy is done by terminating existing pods before creating new ones. This strategy will cause downtime when all of the old pods have been terminated but the new ones haven't been created or are in the process of being created.

4. There are many benefits to using Kubernetes manifest files. It allows the deployment to be automated. Other than that, it also allows for the configuration to be well documented before deployment to prevent mistakes. It also makes redoing deployment simpler and easier.  