all: minikube/start minikube/enable-dashboard kubectl/apply
clean: kubectl/delete minikube/delete
build: docker/build/app docker/build/db
push: docker/push/app docker/push/db
get_ip:
	minikube service app --url

images := app db
images_build_targets := $(addprefix docker/build/,$(images))
images_push_targets := $(addprefix docker/push/,$(images))

$(images_build_targets): docker/build/%:
	docker build -t navjig/$*:cloud-computing $*

# requires proper docker login
$(images_push_targets): docker/push/%:
	docker push navjig/$*:cloud-computing

minikube_cmd := start stop delete
minikube_cmd_targets := $(addprefix minikube/,$(minikube_cmd))

$(minikube_cmd_targets): minikube/%:
	minikube $*

minikube/enable-dashboard:
	minikube addons enable metrics-server

kubectl/apply: manifest.yaml
	kubectl apply -f manifest.yaml

kubectl/delete:
	kubectl delete -n default deployment app
	kubectl delete -n default deployment db
	kubectl delete -n default service app
	kubectl delete -n default service db
	kubectl delete -n default persistentvolumeclaim db-volume
	kubectl delete -n default configmap app-config
	kubectl delete -n default configmap db-config

kubectl/get/nodes:
	kubectl get nodes -o wide

kubectl/get/svc:
	kubectl get svc

kubectl/get/pods:
	kubectl get pods -A

.PHONY: all clean build push get_ip \
 	$(minikube_cmd_targets) minikube/enable-dashboard \
	kubectl/apply kubectl/delete \
	kubectl/get/nodes kubectl/get/svc kubectl/get/pods \
	$(docker_build_targets) $(docker_push_targets)
