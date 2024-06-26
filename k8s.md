kubectl create deployment redis --image=redis
kubectl create deployment rng --image=dockercoins/rng:v0.1
kubectl create deployment hasher --image=dockercoins/hasher:v0.1
kubectl create deployment worker --image=dockercoins/worker:v0.1

kubectl expose deployment redis --port 6379
kubectl expose deployment hasher --port 80
kubectl expose deployment rng --port 80

kubectl scale deployment worker --replicas 3


kubectl expose deployment db --port=5432
kubectl expose deployment web --port=80 --type=NodePort
kubectl expose deployment api --port=8080

or 

kubectl create service clusterip db --tcp=5432
kubectl create service nodeport web --tcp=80
kubectl create service clusterip api --tcp=8080
