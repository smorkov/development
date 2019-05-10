# Shopware development template

This repository is a template for local development. It enables you to create a running Shopware instance to test new technologies from shopware, including the new *core* or the new *administration*.

The newest installation guide, together with the complete documentation, is available at
[docs.shopware.com](https://docs.shopware.com/en/shopware-platform-en/getting-started).
# Steps to install

1. git clone https://github.com/smorkov/development.git
2. cd development
3. git clone https://github.com/shopware/platform.git


Open PowerShell and run the following commands:

mkdir -p $HOME/.composer

mkdir -p $HOME/.npm

docker volume create app_server_mysql

docker volume create app_server_data

---copy provided keys folder to /dev-ops/docker/containers/ssh----

docker-compose build

docker-compose up -d

docker cp ./ development_app_data_1:/app

docker exec development_app_server_1 /bin/sh -c "./psh.phar install"

docker exec development_app_server_1 /bin/sh -c "chown application:application /app -Rf"

Then go to http://localhost:8000 and check if everything is okay
