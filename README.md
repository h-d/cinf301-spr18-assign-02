# cinf301-spr18-assign-02
Docker and MySQL

Docker Ubuntu Container Commands:

docker run --name mysql-3306 -e MYSQL_ROOT_PASSWORD=secret
docker run -d -name ubuntu-test --link mysql-3306 ubuntu

(in ubuntu-test)
apt update && apt upgrade
apt install ifconfig
cat etc/hosts
mysql -h 172.17.0.2 -P 3306 --protocol=tcp -u root -p


Docker LAMP Container Commands:

docker build -t mylampimage .
docker run -itd -p 8080:80 -v "$PWD/app":/var/www/html --name lampcontainer mylampimage
docker exec -itd lampcontainer bash

(in lampcontainer)
mysql
show databases;
create database lamps;
create user 'lamplord'@'localhost' identified by 'lamp';
grant all on lamps.* to 'lamplord'@'localhost';
use lamps;
create table merchandise (id int(10) auto_increment primary key, name varchar(30) not null, shade varchar(30) not null, bulb_type varchar(30), bulb_wattage int(5), antique char(1), price decimal(8,2));
(for all inserts): insert into merchandise (name, shade, bulb_type, bulb_wattage, antique, price) values (NAME, SHADE, BULB, WATTS, ANTIQUE Y/N, PRICE)
select * from merchandise;





