# docker_compose_config_NGINX_PHP
My training simple php config with docker compose

Your need docker and docker-compose in your operation system.

CLONE:
git clone https://github.com/codesshaman/docker_nginx_php_certbot.git

GO TO FOLDER:
cd docker_nginx_php_certbot

GET LETSENCRYPT SCRIPT:

curl -L https://raw.githubusercontent.com/wmnnd/nginx-certbot/master/init-letsencrypt.sh > init-letsencrypt.sh
chmod +x init-letsencrypt.sh

EDIT LETSENCRYPT SCRIPT:

Choose your domain addres and email in next section on file:

domains=(example.org www.example.org)
rsa_key_size=4096
data_path="./data/certbot"
email=""
staging=0

GET CERTIFICATE:

./init-letsencrypt.sh

BUILD (first start):
docker-compose up -d --build

RUN:
docker-compose up -d

STOP:
docker-compose down

CONNECT:
docker exec -it nginx_simple_php sh

OPEN:
http://localhost/