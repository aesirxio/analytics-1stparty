# 1st party server for AesirX Analytics

## What is this

This is your own 1st party server for storing analytics of your websites, thanks to [AesirX Analytics](https://analytics.aesirx.io).

Technically, will need Docker Compose for running the [AesirX 1st Party Server](https://hub.docker.com/r/aesirxio/analytics-1stparty) Docker image, that will store your website analytics data in a MongoDB server (included in the Docker Compose file).

## Technical requirements

1. Docker.
1. Docker Compose.  [Setup instructions](https://docs.docker.com/compose/install/)

### Optional technical requirements

You can also specify your own MongoDB server for storing analytics.  MongoDB 6.x is required.

## Instructions for setting up

1. Clone the `aesirx-1stparty.env.dist` file into `aesirx-1stparty.env` and customize
    * You can choose not to customize anything.
    * If you have a separate MongoDB server, you can specify the credentials using the following variables:
        * DBUSER
        * DBPASS
        * DBHOST
        * DBPORT
        * DBNAME
    * You can choose to change the HTTP_PORT variable (default 80).  Please keep in mind that this port is the one inside the container, so it's a beter idea if you don't change it.
1. Clone the `.env.dist` file into `.env` and customize.
    * You can customize your ports:
        * HTTP_PORT: published port of the server.  If you want your server to listen to a different port, this is the configuration that you need to change.
        * MONGO_PORT: published port for MongoDB
    * You can customize your DB settings (they need to be the same as in the `aesirx-1stparty.env` file).
        * MONGO_INITDB_ROOT_USERNAME
        * MONGO_INITDB_ROOT_PASSWORD
        * MONGO_INITDB_DATABASE
1. Execute `docker compose up -d` to run the full setup, including the MongoDB server.
