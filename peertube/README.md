# Peertube

> Free and open-source, decentralized, federated video platform

```
cp .env.sample .env
# Change the value in .env with your configuration

mkdir -p ./volumes/{data,config,db,redis}
docker-compose up -d
```

Update procedure
```
docker-compose pull
docker-compose down -v
docker-compose up -d
```
Git repository: https://github.com/Chocobozzz/PeerTube
