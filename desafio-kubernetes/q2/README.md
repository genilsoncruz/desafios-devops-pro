docker build -t genilsoncruz/conversao-peso:v1 -f ./Dockerfile ./conversao-peso/ConversaoPeso.Web

docker push genilsoncruz/conversao-peso:v1

docker tag genilsoncruz/conversao-peso:v1 genilsoncruz/conversao-peso:latest

docker push genilsoncruz/conversao-peso:latest

kubectl apply -f q2-deployment.yaml -f q2-service.yaml

kubectl port-forward pod/conversao-peso-6895988d5-8cdr9 8080:80

kubectl delete -f q2-deployment.yaml -f q2-service.yaml