### The .yml is a modified version from [pyflink_learn](https://github.com/uncleguanghui/pyflink_learn)   

##Install Docker:   
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh --mirror Aliyun   
sudo systemctl enable docker   
sudo systemtcl start docker   
mkdir -p /etc/docker   
sudo vi /etc/docker/daemon.json   
{
  "registry-mirrors":["https://docker.mirrors.ustc.edu.cn"]
}
sudo systemctl daemon-reload   
sudo systemctl restart docker   
### docker UI   
sudo docker pull portainer/portainer   
sudo docker volume create portainer_data   
sudo docker run -d -p 9000:9000 --name portainer --restart always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer   
 
## Install emqx using docker   
sudo docker pull emqx/emqx:4.3.10   
sudo docker run -d --name emqx -p 1883:1883 -p 8081:8081 -p 8083:8083 -p 8084:8084 -p 8883:8883 -p 18083:18083 emqx/emqx:4.3.10   
UI port: 18083; default user: admin; default password: public   

## install airflow   
pip3 install apache-airflow   
airflow db init   
airflow webserver -p 8080 -D   
airflow scheduler -D   
airflow users create   
UI port: 8080  

## install postgresql   
sudo apt install postgresql libpq-dev postgresql-client postgresql-client-common -y   
sudo su postgres   
createuser pi -P --interactive   
first enter 'n' then 'y' and 'y'   
enter psql   
create database test;   
enter twice "Ctrl+D", then enter: su pi      
login pg and access db using the created pg user "pi": psql test   


