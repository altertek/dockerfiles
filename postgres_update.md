# PostgresSQL docker update procedure

docker compose up -d postgres

docker compose exec -t postgres pg_dumpall -U peertube > pgXX_dump.sql

docker compose down

mv ./volumes/db ./volumes/db.pgXX.old
mkdir -p ./volumes/db

# Update PG version in docker-compose file

docker compose up -d postgres

cat peertube_pgXX_dump.sql | docker compose exec -i postgres psql -U peertube

docker compose exec -it postgres psql -U peertube -c '\dt'

# Check that everything works
docker compose up -d 
