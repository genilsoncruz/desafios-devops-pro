docker build -t genilsoncruz/pedelogo-catalogo:v1 -f ./Dockerfile ./pedelogo-catalogo/

docker push genilsoncruz/pedelogo-catalogo:v1

docker tag genilsoncruz/pedelogo-catalogo:v1 genilsoncruz/pedelogo-catalogo:latest

docker push genilsoncruz/pedelogo-catalogo:latest

kubectl apply -f q4-deployment.yaml -f q4-deployment-service.yaml -f q4-mongodb.yaml -f q4-mongodb-service.yaml

kubectl port-forward $(kubectl get --no-headers=true pods -o name --selector=app=pedelogo-catalogo) 8080:80
kubectl port-forward $(kubectl get --no-headers=true pods -o name --selector=app=pedelogo-catalogo) 8443:443

kubectl delete -f q4-deployment.yaml -f q4-deployment-service.yaml -f q4-mongodb.yaml -f q4-mongodb-service.yaml