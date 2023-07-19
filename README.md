# Prometheus-Grafana
1- made kind create cluster --name=test
2- then watched the nodes by using kubectl get nodes --watch
3- we used the helm repo add prometheus-community https://prometheus-community.github.io/helm-charts/
4- helm repo update. 
5- I created a namespace called monitoring by using kubectl create namespace monitoring.
6- helm install prometheus prometheus-community/kube-prometheus-stack -n monitoring
7- then checked if its working by using kubectl --namespace monitoring get pods -l "release=prometheus"
8- Then downloaded ngrok by using 
wget https://bin.equinox.io/c/bNyj1mQVY4c/ngrok-v3-stable-linux-amd64.tgz 
tar -zxvf ngrok-v3-stable-linux-amd64.tgz
./ngrok config add-authtoken 2RKvl49DN8cgRKccnyBPXhJPEOC_2nDRSH43uXaZzGnTKxSNu

9- checked the connection using kubectl port-forward service/prometheus-kube-prometheus-prometheus 9090 -n monitoring &./ngrok http 0.0.0.0:9090

10- Downloaded this repo and worked by using these commands and have 
git clone https://gitlab.com/devopsandy/youtube-tutorial-series.git
11- helm install redis bitnami/redis
12- kubectl apply -f redis-master-deployment.yaml
13- kubectl apply -f redis-master-servive.yaml 
14- kubectl get deploy
15- kubectl get svc
16- kubectl apply -f redis.yaml
17- kubectl apply -f servicemonitor.yaml
18- kubectl get deploy 
19- kubectl get svc
20- helm install redis-exporter prometheus-community/prometheus-redis-exporter -f prometheus-redis_values.yaml
21- kubectl get servicemonitor

malakeh@Prometheus-Grafana:~$ cd youtube-tutorial-series/
malakeh@Prometheus-Grafana:~/youtube-tutorial-series$ ls
basic-kubectl-commands                  kubernetes-configuration-file-explained  pull-images-from-private-reporsitory-in-k8s
configmap-and-secret-volumes            kubernetes-ingress                       README.md
container-communication-k8s-networking  kubernetes-volumes                       setup-prometheus-operator
demo-kubernetes-components              linode-kubernetes-engine-demo
github-actions                          prometheus-exporter

malakeh@Prometheus-Grafana:~/youtube-tutorial-series$ cd prometheus-exporter/
malakeh@Prometheus-Grafana:~/youtube-tutorial-series/prometheus-exporter$ ls
commands.md                     mongodb.yaml                  prometheus-redis_values.yaml  redis-master-service.yaml
install-prometheus-commands.md  prometheus-exporter_redis.md  redis-master-deployment.yaml  values.yaml
malakeh@Prometheus-Grafana:~/youtube-tutorial-series/prometheus-exporter$

To enter the Grafana dashboard used this command to redirect the communication via HTTP protocol to ngrok service and access it by the wan.

kubectl port-forward service/prometheus-grafana 8080:80 --address='0.0.0.0' &/home/malakeh/ngrok http 0.0.0.0:8080

after reaching the dashboard we got the dashboard that contains all the recources information like CPU, Memory and bandwidth by clicking on Dashboards > Playlists > New Playlist and filling the name and selecting the dashboard the just save it and play it. 
