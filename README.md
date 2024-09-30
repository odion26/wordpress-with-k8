# wordpress-with-k8
Installing wordpress with Kubernetes

# Creating mysql credential
kubectl create secret generic mysql-credentials \
--from-literal=MYSQL_ROOT_PASSWORD=<mysql_root_password> \
--from-literal=MYSQL_DATABASE=<mysql_dbname> \
--from-literal=MYSQL_USER=<mysql_user> \
--from-literal=MYSQL_PASSWORD=<mysql_password>
