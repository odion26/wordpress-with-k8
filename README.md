# Installing wordpress with Kubernetes

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
