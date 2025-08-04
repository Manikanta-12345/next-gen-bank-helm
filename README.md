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

gcloud container clusters get-credentials autopilot-cluster-1 --region asia-south1

gcloud container clusters update cluster-1 \
 --disable-managed-prometheus \
 --zone us-central1

gcloud container clusters resize cluster-1 \
 --node-pool=default-pool \
 --num-nodes=5 \
 --zone=us-central1

https://www.youtube.com/watch?v=JGQI5pkK82w&t=301s
https://github.com/iam-veeramalla/Jenkins-Zero-To-Hero/blob/main/java-maven-sonar-argocd-helm-k8s/spring-boot-app/JenkinsFile

argocd pwd:
ovmQN0n8n9srCnX3
kubectl port-forward svc/argocd-server 8888:443 -n argocd

https://github.com/Manikanta-12345/next-gen-bank-helm.git

kubectl create secret generic mysql-secret \
 --from-literal=mysql-root-password=nextgenroot@123 \
 --from-literal=mysql-password=YourAppPassword \
 --from-literal=mysql-replication-password=YourReplicationPassword

echo -n 'your-password' | base64

/Users/manikanta/.zshrc:1: command not found: RC
manikanta@Manikantas-MacBook-Air NextGenBankHelm % echo -n 'nextgenroot@123' | base64
bmV4dGdlbnJvb3RAMTIz
manikanta@Manikantas-MacBook-Air NextGenBankHelm % echo -n 'nextgen@123' | base64
bmV4dGdlbkAxMjM=
manikanta@Manikantas-MacBook-Air NextGenBankHelm %

# MYSQL

NAME: nextgen-mysql
LAST DEPLOYED: Mon Aug 4 14:19:06 2025
NAMESPACE: default
STATUS: deployed
REVISION: 1
TEST SUITE: None
NOTES:
CHART NAME: mysql
CHART VERSION: 14.0.0
APP VERSION: 9.4.0

⚠ WARNING: Since August 28th, 2025, only a limited subset of images/charts are available for free.
Subscribe to Bitnami Secure Images to receive continued support and security updates.
More info at https://bitnami.com and https://github.com/bitnami/containers/issues/83267

** Please be patient while the chart is being deployed **

Tip:

Watch the deployment status using the command: kubectl get pods -w --namespace default

Services:

echo Primary: nextgen-mysql.default.svc.cluster.local:3306

Execute the following to get the administrator credentials:

echo Username: root
MYSQL_ROOT_PASSWORD=$(kubectl get secret --namespace default mysql-auth -o jsonpath="{.data.mysql-root-password}" | base64 -d)

To connect to your database:

1. Run a pod that you can use as a client:

   kubectl run nextgen-mysql-client --rm --tty -i --restart='Never' --image docker.io/bitnami/mysql:9.4.0-debian-12-r0 --namespace default --env MYSQL_ROOT_PASSWORD=$MYSQL_ROOT_PASSWORD --command -- bash

2. To connect to primary service (read/write):

   mysql -h nextgen-mysql.default.svc.cluster.local -uroot -p"$MYSQL_ROOT_PASSWORD"

WARNING: There are "resources" sections in the chart not set. Using "resourcesPreset" is not recommended for production. For production installations, please set the following values according to your workload needs:

- primary.resources
- secondary.resources
  +info https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/

#Keycloak

NAME: keycloak
LAST DEPLOYED: Mon Aug 4 11:31:52 2025
NAMESPACE: default
STATUS: deployed
REVISION: 1
TEST SUITE: None
NOTES:
CHART NAME: keycloak
CHART VERSION: 24.4.3
APP VERSION: 26.0.8

Did you know there are enterprise versions of the Bitnami catalog? For enhanced secure software supply chain features, unlimited pulls from Docker, LTS support, or application customization, see Bitnami Premium or Tanzu Application Catalog. See https://www.arrow.com/globalecs/na/vendors/bitnami for more information.

** Please be patient while the chart is being deployed **

Keycloak can be accessed through the following DNS name from within your cluster:

    keycloak.default.svc.cluster.local (port 80)

To access Keycloak from outside the cluster execute the following commands:

1. Get the Keycloak URL by running these commands:

   export HTTP_NODE_PORT=$(kubectl get --namespace default -o jsonpath="{.spec.ports[?(@.name=='http')].nodePort}" services keycloak)
    export NODE_IP=$(kubectl get nodes --namespace default -o jsonpath="{.items[0].status.addresses[0].address}")

   echo "http://${NODE_IP}:${HTTP_NODE_PORT}/"

2. Access Keycloak using the obtained URL.
3. Access the Administration Console using the following credentials:

echo Username: user
echo Password: $(kubectl get secret --namespace default keycloak -o jsonpath="{.data.admin-password}" | base64 -d)

WARNING: There are "resources" sections in the chart not set. Using "resourcesPreset" is not recommended for production. For production installations, please set the following values according to your workload needs:

- resources
  +info https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/

#KAFKA
NAME: kafka
LAST DEPLOYED: Mon Aug 4 17:18:15 2025
NAMESPACE: default
STATUS: deployed
REVISION: 1
TEST SUITE: None
NOTES:
CHART NAME: kafka
CHART VERSION: 32.3.10
APP VERSION: 4.0.0

⚠ WARNING: Since August 28th, 2025, only a limited subset of images/charts are available for free.
Subscribe to Bitnami Secure Images to receive continued support and security updates.
More info at https://bitnami.com and https://github.com/bitnami/containers/issues/83267

** Please be patient while the chart is being deployed **

Kafka can be accessed by consumers via port 9092 on the following DNS name from within your cluster:

    kafka.default.svc.cluster.local

Each Kafka broker can be accessed by producers via port 9092 on the following DNS name(s) from within your cluster:

    kafka-controller-0.kafka-controller-headless.default.svc.cluster.local:9092
    kafka-controller-1.kafka-controller-headless.default.svc.cluster.local:9092

To create a pod that you can use as a Kafka client run the following commands:

    kubectl run kafka-client --restart='Never' --image docker.io/bitnami/kafka:4.0.0-debian-12-r8 --namespace default --command -- sleep infinity
    kubectl exec --tty -i kafka-client --namespace default -- bash

    PRODUCER:
        kafka-console-producer.sh \
            --bootstrap-server kafka.default.svc.cluster.local:9092 \
            --topic test

    CONSUMER:
        kafka-console-consumer.sh \
            --bootstrap-server kafka.default.svc.cluster.local:9092 \
            --topic test \
            --from-beginning

WARNING: There are "resources" sections in the chart not set. Using "resourcesPreset" is not recommended for production. For production installations, please set the following values according to your workload needs:

- controller.resources
- defaultInitContainers.prepareConfig.resources
  +info https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/

kubectl get secrets argocd-initial-admin-secret -n argocd -o yaml
