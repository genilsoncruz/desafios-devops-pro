docker build -t genilsoncruz/conversao-temperatura:v1 -f ./Dockerfile ./conversao-temperatura/src

docker push genilsoncruz/conversao-temperatura:v1

docker tag genilsoncruz/conversao-temperatura:v1 genilsoncruz/conversao-temperatura:latest

docker push genilsoncruz/conversao-temperatura:latest

kubectl apply -f q1-deployment.yaml -f q1-service.yaml

kubectl port-forward pod/conversao-temperatura-5975954f46-l55vh 8080:8080

kubectl delete -f q1-deployment.yaml -f q1-service.yaml