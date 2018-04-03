# cinf301-spr18-assign-02
Docker and MySQL

Docker Container Commands:

docker run --name mysql-3306 -e MYSQL_ROOT_PASSWORD=secret
docker run -d -name ubuntu-test --link mysql-3306 ubuntu

(in ubuntu-test)
apt update && apt upgrade
apt install ifconfig
cat etc/hosts
mysql -h 172.17.0.2 -P 3306 --protocol=tcp -u root -p



