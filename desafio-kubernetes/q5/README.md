docker build -t genilsoncruz/rotten-potatoes:v1 -f ./Dockerfile ./rotten-potatoes/src

docker push genilsoncruz/rotten-potatoes:v1

docker tag genilsoncruz/rotten-potatoes:v1 genilsoncruz/rotten-potatoes:latest

docker push genilsoncruz/rotten-potatoes:latest

kubectl apply -f q5-deployment.yaml -f q5-deployment-service.yaml -f q5-mongodb.yaml -f q5-mongodb-service.yaml

kubectl port-forward $(kubectl get --no-headers=true pods -o name --selector=app=rotten-potatoes) 5000:5000

kubectl delete -f q5-deployment.yaml -f q5-deployment-service.yaml -f q5-mongodb.yaml -f q5-mongodb-service.yaml