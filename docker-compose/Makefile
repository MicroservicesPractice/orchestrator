.PHONY: help
help: # Show help for each of the Makefile recipes.
	@grep -E '^[a-zA-Z0-9 -]+:.*#'  Makefile | sort | while read -r l; do printf "\033[1;32m$$(echo $$l | cut -f 1 -d':')\033[00m:$$(echo $$l | cut -f 2- -d'#')\n"; done

.PHONY: run
run: # Run the whole app in docker containers 
	docker compose -f ./docker-compose.yaml up -d 

.PHONY: build
build: # Build or rebuild containers
	docker compose -f ./docker-compose.yaml build

.PHONY: down
down: # Stop docker containers
	docker compose -f ./docker-compose.yaml down 

.PHONY: prune
prune: # Stop docker containers
	docker compose -f ./docker-compose.yaml down -v

.PHONY: rm
rm: # Stop docker containers
	docker compose -f ./docker-compose.yaml rm --all

.PHONY: db
db: # Stop docker containers
	docker exec -it postgres-db bash 

.PHONY: installKind
installKind: # install kind
	go install sigs.k8s.io/kind@v0.22.0 

.PHONY: createCluster
createCluster: # create cluster with kind
	kind create cluster 