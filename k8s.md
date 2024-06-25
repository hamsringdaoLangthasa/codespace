kubectl create deployment redis --image=redis
kubectl create deployment rng --image=dockercoins/rng:v0.1
kubectl create deployment hasher --image=dockercoins/hasher:v0.1
kubectl create deployment worker --image=dockercoins/worker:v0.1

kubectl expose deployment redis --port 6379
kubectl expose deployment hasher --port 80
kubectl expose deployment rng --port 80

kubectl scale deployment worker --replicas 3