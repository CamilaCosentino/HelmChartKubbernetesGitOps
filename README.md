# Desafio 9
## Primero creamos una imagen de Docker que vamos a usar
#### Esta es la arquitectura que se uso
<img width="420" alt="Captura de Pantalla 2023-10-31 a la(s) 09 56 24 p  m" src="https://github.com/CamilaCosentino/HelmChartKubbernetesGitOps/assets/89109209/7b40904e-013e-44d7-afd1-29466e42adbb">


### Construimos la imagen
```bash
docker build -t app-chat:1.0.0 -f ./Dockerfile .
```
<img width="1008" alt="Captura de Pantalla 2023-10-31 a la(s) 10 01 26 p  m" src="https://github.com/CamilaCosentino/HelmChartKubbernetesGitOps/assets/89109209/6c1b5806-3a59-450a-85a0-6ce973b0e04f">

### Renombramos la imagen para subirla a Docker Hub
```bash
docker tag app-chat:1.0.0 camila232dmnfdn2i/app-chat:1.0.0
```
<img width="1197" alt="Captura de Pantalla 2023-10-31 a la(s) 09 59 34 p  m" src="https://github.com/CamilaCosentino/HelmChartKubbernetesGitOps/assets/89109209/1475bd37-142d-4c06-a933-fdad61958b80">


### Publicamos la imagen
```bash
docker push camila232dmnfdn2i/app-chat:1.0.0
```
<img width="1365" alt="Captura de Pantalla 2023-10-31 a la(s) 10 02 03 p  m" src="https://github.com/CamilaCosentino/HelmChartKubbernetesGitOps/assets/89109209/febd37f0-c25f-4230-bebe-c131c18f13bb">

## Crear archivos de helm chart
```bash
helm create pythonapp-helm-chart
```
Esto te crea unos determinados directiorios y archivos

<img width="417" alt="Captura de Pantalla 2023-11-02 a la(s) 07 55 47 p  m" src="https://github.com/CamilaCosentino/HelmChartKubbernetesGitOps/assets/89109209/977a7b44-11b5-43e8-80ee-60c54055133c">

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
