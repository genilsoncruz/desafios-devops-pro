docker build -t genilsoncruz/kube-news:v1 -f ./Dockerfile ./kube-news/src

docker push genilsoncruz/kube-news:v1

docker tag genilsoncruz/kube-news:v1 genilsoncruz/kube-news:latest

docker push genilsoncruz/kube-news:latest

kubectl apply -f q6-deployment.yaml -f q6-deployment-service.yaml -f q6-postgres.yaml -f q6-postgres-service.yaml

kubectl port-forward $(kubectl get --no-headers=true pods -o name --selector=app=kube-news) 8080:8080

kubectl delete -f q6-deployment.yaml -f q6-deployment-service.yaml -f q6-postgres.yaml -f q6-postgres-service.yaml