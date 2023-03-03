docker build -t genilsoncruz/conversao-distancia:v1 .

docker push genilsoncruz/conversao-distancia:v1

docker tag genilsoncruz/conversao-distancia:v1 genilsoncruz/conversao-distancia:latest

docker push genilsoncruz/conversao-distancia:latest

kubectl apply -f q3-deployment.yaml -f q3-service.yaml

kubectl port-forward pod/conversao-distancia-647dbd6d6b-vd9tw 8080:80