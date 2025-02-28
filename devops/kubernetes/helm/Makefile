run.superset:
	helm upgrade --install --values configs/values.yaml superset superset/superset
run.redis:
	helm install superset-redis oci://registry-1.docker.io/bitnamicharts/redis
run.postgresql:
	helm install superset-postgresql oci://registry-1.docker.io/bitnamicharts/postgresql
postgresql.secret:
	kubectl create secret generic postgresql-password --from-literal=password=superset --from-literal=postgres-password=superset --dry-run -o yaml | kubectl apply -f -

delete.superset:
	helm delete superset

upgrade.superset:
	helm upgrade --values configs/values.yaml superset superset/superset

proxy.superset:
	kubectl port-forward service/superset 8088:8088 --namespace default
