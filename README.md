# Desafio 9
## Primero creamos una imagen de Docker que vamos a usar

### Construimos la imagen
```bash
docker build -t app-chat:1.0.0 -f ./Dockerfile .
```

### Renombramos la imagen para subirla a Docker Hub
```bash
docker tag app-chat:1.0.0 camila232dmnfdn2i/app-chat:1.0.0
```


### Publicamos la imagen
```bash
docker push camila232dmnfdn2i/app-chat:1.0.0
```


## Crear archivos de helm chart
```bash
helm create pythonapp-helm-chart
```
Esto te crea unos determinados directiorios y archivos



## Crear repositorio de ArgoCD en Helm
```bash
helm repo add argo https://argoproj.github.io/argo-helm
```
## Instalamos el repositorio
```bash
helm install argocd argo/argo-cd -n argocd
```
## Revisamos que se instaló
```bash
helm repo list -n agrocd
```
## argoCD port-forward.
```bash
kubectl port-forward svc/argocd-server -n argo-cd 8080:443
```

# Para crear la aplicación en Argo
```bash
kubectl apply -f application.yaml
```
Esto se hace posicionado en la carpeta /argocd

