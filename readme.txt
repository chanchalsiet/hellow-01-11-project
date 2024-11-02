## ArgoCD deployment POC on Kubernetes


### Sample commands

1. Create a simple flask app
2. Create a DockerFile
3. Build multi arch Docker image
```bash
docker buildx build -t hellow-01-11-images .

## building for multiplatform
docker buildx build --platform linux/amd64,linux/arm64 -t us-central1-docker.pkg.dev/elastiq-internship-chanchal-01/hello-repo/helloworld-gke:latest .
docker buildx build --platform linux/amd64,linux/arm64 -t hellow-01-11-images .

```
4. Run the docker image on local
```bash
docker run -e PORT=8000 -p 8082:8000 hellow-01-11-images:latest
```

4. Install Gcloud SDK
5. Push the Docker image to GCP Artifact registry
```bash

docker tag chanchal:2.0 us-central1-docker.pkg.dev/elastiq-internship-chanchal-01/hello-repo/helloworld-gke:latest
docker push us-central1-docker.pkg.dev/elastiq-internship-chanchal-01/hello-repo/helloworld-gke:latest

```
6. Push the Docker image to Docker hub

7. Pull image from GCP artifact registry
8. Pull image from Docker hub


### References
1. [ArgoCD Getting Started Gudie](https://argo-cd.readthedocs.io/en/stable/getting_started/)