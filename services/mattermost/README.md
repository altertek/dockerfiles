# Mattermost

> Online chat service with file sharing, search, and integrations

```
cp .env.sample .env
# Change the values in .env with your configuration

mkdir -p ./volumes/mattermost-{data,config,plugins}
chown -R 2000:2000 ./volumes/
docker-compose up -d
```

Git repository: https://github.com/mattermost/docker
