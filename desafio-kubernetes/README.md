#Container Resistry hub.docker.com

gpg --generate-key
pass init <generated gpg-id public key>

docker logout

docker login

watch 'kubectl get all'