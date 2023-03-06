cd q5/rotten-potatoes/src

docker build -t genilsoncruz/rotten-potatoes:v1 .

docker push genilsoncruz/rotten-potatoes:v1

docker tag genilsoncruz/rotten-potatoes:v1 genilsoncruz/rotten-potatoes:latest

docker push genilsoncruz/rotten-potatoes:latest

cd ../../

kubectl apply -f q5-deployment.yaml -f q5-deployment-service.yaml -f q5-mongodb.yaml -f q5-mongodb-service.yaml

kubectl port-forward pod/rotten-potatoes-deployment-b6859d59b-wbgw7 5000:5000