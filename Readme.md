# ghost-nodejs-docker
A ghost nodejs website docker-compose serve with nginx

## Add below domain mapping in /etc/hosts
127.0.0.1 ghost-auzmor.com

## Running application
docker-compose up -d

## Generating ssl certifacte
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout ssl/ghost.key -out ssl/ghost.crt

## Generating dhparam key
openssl dhparam 2048 -out ssl/ghost.pem

## Finding issuer
openssl s_client -connect ghost-auzmor.com:443 -status | grep "issuer"
