# Mattermost

> Online chat service with file sharing, search, and integrations

```
cp .env.sample .env
# Change the values in .env with your configuration

mkdir -p ./volumes/mattermost-{data,config,plugins}
chown -R 2000:2000 ./volumes/
docker-compose up -d
```

Fork repository: https://framagit.org/framasoft/framateam/mostlymatter/-/tree/master
Docker Image source: https://github.com/this-is-tobi/multiarch-mirror
Git repository: https://github.com/mattermost/docker
