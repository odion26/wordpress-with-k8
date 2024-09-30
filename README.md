# Installing wordpress with Kubernetes

git clone 

**Creating mysql credential**  
kubectl create secret generic mysql-credentials \
--from-literal=MYSQL_ROOT_PASSWORD=<mysql_root_password> \
--from-literal=MYSQL_DATABASE=<mysql_dbname> \
--from-literal=MYSQL_USER=<mysql_user> \
--from-literal=MYSQL_PASSWORD=<mysql_password>

**Creating wordpress credential**  
kubectl create secret generic wordpress-credentials \
--from-literal=WORDPRESS_DB_HOST=mysql \
--from-literal=WORDPRESS_DB_NAME=<wordpress_db_name> \
--from-literal=WORDPRESS_DB_USER=<wordpressd_db_user> \
--from-literal=WORDPRESS_DB_PASSWORD=<wordpress_db_password>

**Create mysql deployment**  
kubectl apply -f mysql-deployment.yaml

**create wordpress deployment**  
kubectl apply -f wordpress-deployment.yaml

**Create service port forwordpress and mysql**   
kubectl expose deployment wordpress --type=NodePort --port=80  
kubectl expose deployment mysql --type=NodePort --port=3306  
kubectl get svc  

**output**
![image](https://github.com/user-attachments/assets/cdd43a28-2c9c-40bc-af85-3368d6fd53f8)


**Accessing wordpress**  
IP_Address:wordpress_Nodeport  
192.168.1.155:31121  

![image](https://github.com/user-attachments/assets/16bed103-9b22-4121-a55b-2969f897b547)


