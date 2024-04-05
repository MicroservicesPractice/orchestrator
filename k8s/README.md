# kind commands
To use this config, place the contents in a file config.yaml and then run kind create cluster --config=config.yaml from the same directory.
## kind create cluster --config=config.yaml

Now our custom Docker image is ready and we can load to our Kubernetes cluster
## kind load docker-image my-app:v1 --name dev
We can get a list of images loaded in our cluster using the below command
## docker container exec -it dev-control-plane crictl images

# kubectl commands
- config location ~/.kube/config 
- Run the following command to set the default namespace:
## kubectl config set-context --current --namespace=<your-namespace>


# DOCKER
docker buildx build  -t k8s-postgres .