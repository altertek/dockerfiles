# Matrix Synapse

> Decentralised messaging

```
cp .env.sample .env
# Change the values in .env with your configuration

mkdir -p ./volumes/{data,postgres}

# Initiate the database
docker-compose run --rm -e SYNAPSE_SERVER_NAME=EXAMPLE.COM -e SYNAPSE_REPORT_STATS=yes synapse generate

```

This is not over! For some reason we need to dig in the config file to setup postgres  
Edit the database section in the config file ./volumes/data/homeserver.yaml
```
database:
  name: psycopg2
  args:
    user: matrix
    password: CHANGE_ME
    database: matrix
    host: db
    cp_min: 5
    cp_max: 10
```

Now start the containers
```
docker-compose up -d

```

Finally, Create an admin user
```
docker-compose exec synapse register_new_matrix_user http://localhost:8008 -c /data/homeserver.yaml -a -u myuser -p mypassword
```

Git repository: https://github.com/matrix-org/synapse/

Docker infos: https://github.com/matrix-org/synapse/blob/develop/docker/README.md#generating-a-configuration-file
