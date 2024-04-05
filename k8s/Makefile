.PHONY: help
help: # Show help for each of the Makefile recipes.
	@grep -E '^[a-zA-Z0-9 -]+:.*#'  Makefile | sort | while read -r l; do printf "\033[1;32m$$(echo $$l | cut -f 1 -d':')\033[00m:$$(echo $$l | cut -f 2- -d'#')\n"; done

.PHONY: installKind
installKind: # install kind
	go install sigs.k8s.io/kind@v0.22.0 

.PHONY: createCluster
createCluster: # create cluster with kind
	kind create cluster --config=config-cluster.yaml

.PHONY: setDevCtx
setDevCtx: # create cluster with kind
	 kubectl config set-context --current --namespace=dev

.PHONY: applyAll
applyAll: # create cluster with kind
	 kubectl apply -f ./namespaces -f ./deploy/pg4admin -f ./deploy/postgres