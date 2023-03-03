docker build -t genilsoncruz/conversao-temperatura:v1 .

docker push genilsoncruz/conversao-temperatura:v1

docker tag genilsoncruz/conversao-temperatura:v1 genilsoncruz/conversao-temperatura:latest

docker push genilsoncruz/conversao-temperatura:latest

kubectl apply -f q1-deployment.yaml -f q1-service.yaml

kubectl port-forward pod/conversao-temperatura-5975954f46-xgqgx 8080:8080