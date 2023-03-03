docker build -t genilsoncruz/conversao-peso:v1 .

docker push genilsoncruz/conversao-peso:v1

docker tag genilsoncruz/conversao-peso:v1 genilsoncruz/conversao-peso:latest

docker push genilsoncruz/conversao-peso:latest

docker image ls

kubectl apply -f q2-deployment.yaml

kubectl apply -f q2-service.yaml

kubectl port-forward pod/conversao-peso-6895988d5-6x4jl 8080:80