# ExamKubernetes
Examen de conocimiento para kubernetes


# Dockefile
Se especifica el contendor con la imagen base de python:3.7.3-slim, se instala las dependencias y se activa el servicio que arroja un mensaje de "Hello World", se ha subido la imagen en el repositorio DockerHub con el nombre sebasam91/appgateexam

# Application
Se especifica como sera el despliegue en el contenedor de minikube, ejecutar el siguiente comando "kubectl apply -f application/Deployment.yaml" y "kubectl apply -f application/services.yaml.

En el cluster debera crearse con 5 pods, y un servicio tipo nodeport por el puerto 32739. La ip del cluster se puede consultar ejecutando "minikube ip". Para validar que el servicio responde se debe ingresar http://<<ip_cluster>>:32739

# Metricas
Se realizo la prueba para la instalacion de prometheus y grafana en el minikube utilizando los siguientes comandos. 

  helm install prometheus prometheus-community/kube-prometheus-stack --namespace prometheus

Para acceder a la interfaz se ejecuta los siguientes comandos (tener en cuenta el nombre del pod en el cluster): 
  kubectl port-forward -n prometheus prometheus-prometheus-kube-prometheus-prometheus-0 9090
  kubectl port-forward -n prometheus prometheus-grafana-7f678d98c7-zpdm6 3000
  kubectl port-forward -n prometheus prometheus-kube-state-metrics-94f76f559-6ptxn 8080




