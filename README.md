Keycloak Identity management demo
====

This repository is a reference place for quickly getting started with Keycloak.
It doesn't contain much. 

* A docker-compose file to start KeyCloak and Postgres in a dockerised fashion
* Docker Volume based Keycloak theme mounting

Getting Started
=====

Docker compose will bring up a Keycloak service. 
`docker-compose -f local.yml up`

To simplify initial setup, admin account will be auto created with following:
```
        username: admin
        Password: testing
```
After login, please update the password.

### Database

Keycloak supports many database backend. In this demo, we are using Postgres.

### Themes

Keycloak supports themes for the web application. Our custom themes are maintained in themes directory.

#### Enabling proxy address forwarding
When running Keycloak behind a proxy (like NGINX), you will need to enable proxy address forwarding.

`docker run -e PROXY_ADDRESS_FORWARDING=true jboss/keycloak`

#### Debugging keycloak postgres

Connect to the docker container
`docker exec -it keycloak_postgres /bin/sh`

`psql -U keycloak -d keycloak`