# kind commands
To use this config, place the contents in a file config.yaml and then run kind create cluster --config=config.yaml from the same directory.
## kind create cluster --config=config.yaml

Now our custom Docker image is ready and we can load to our Kubernetes cluster
## kind load docker-image k8s-auth-service:v1 --name k8s-cluster

We can get a list of images loaded in our cluster using the below command
## docker container exec -it k8s-cluster-control-plane crictl images

# kubectl commands
- config location ~/.kube/config 
- Run the following command to set the default namespace:
## kubectl config set-context --current --namespace=<your-namespace>


# DOCKER
## docker image build -f Dockerfile -t k8s-registration-service:v1 .

# local DNS redirects 
/etc/hosts