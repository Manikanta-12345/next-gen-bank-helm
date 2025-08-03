# Helm Steps

helm create next-gen-bank-common

helm dependencies build

CONFIGSERVER_URL=localhost
EUREKA_HOST=localhost
KAFKA_BOOTSTRAP_SERVERS=localhost:9092,localhost:9093,localhost:9094;KEYCLOACK_TOKEN_URL=http://localhost:8080/realms/next-gen-bank/protocol/openid-connect/token
KEYCLOACK_USER_URL=http://localhost:8080//admin/realms/next-gen-bank/users
NEXT_GEN_UAMS_CLIENT_SECRET=p3sqTHth08sx8UN5WGmVXkOic83HCyuV
UAMS_DB_HOST=localhost;
UAMS_DB_PASSWORD=root@123;
UAMS_DB_USER=root
KEYCLOACK_JWK_SET_URL=http://localhost:8080/realms/next-gen-bank/protocol/openid-connect/certs
GIT_URI=https://github.com/Manikanta-12345/next-gen-bank-config.git

KAFKA_BOOTSTRAP_SERVERS=localhost:9092,localhost:9093,localhost:9094;NEXT_GEN_ACCOUNTS_DB_HOST=localhost;
NEXT_GEN_ACCOUNTS_DB_PASSWORD=root@123;
NEXT_GEN_ACCOUNTS_DB_USER=root

minikube service next-gen-configserver --url
minikube image load mani12345/next-gen-eureka:s14

https://youtu.be/JGQI5pkK82w?si=x3ZoyE03sLZ_rhmv

Ritesh@2027$$$

Free trial status: ₹26,045.63 credit and 91 days remaining. Activate your full account to get unlimited access to all of Google Cloud—use any remaining credits, then pay only for what you use.

http://34.47.233.46:8080/

gcloud components install gke-gcloud-auth-plugin

gcloud container clusters get-credentials cluster-1 --region us-central1

https://www.youtube.com/watch?v=JGQI5pkK82w&t=301s
https://github.com/iam-veeramalla/Jenkins-Zero-To-Hero/blob/main/java-maven-sonar-argocd-helm-k8s/spring-boot-app/JenkinsFile

ovmQN0n8n9srCnX3
kubectl port-forward svc/argocd-server 8888:443 -n argocd

https://github.com/Manikanta-12345/next-gen-bank-helm.git
