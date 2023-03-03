docker build -t genilsoncruz/pedelogo-catalogo:v1 -f ./pedelogo-catalogo/src/PedeLogo.Catalogo.Api/Dockerfile ./pedelogo-catalogo/

docker push genilsoncruz/pedelogo-catalogo:v1

docker tag genilsoncruz/pedelogo-catalogo:v1 genilsoncruz/pedelogo-catalogo:latest

docker push genilsoncruz/pedelogo-catalogo:latest

kubectl apply -f q4-deployment.yaml -f q4-deployment-service.yaml -f q4-mongodb.yaml -f q4-mongodb-service.yaml

kubectl port-forward pod/pedelogo-catalogo-deployment-59c997c5c-xfd64 8080:80
kubectl port-forward pod/pedelogo-catalogo-deployment-59c997c5c-xfd64 8443:443