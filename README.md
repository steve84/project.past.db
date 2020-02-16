# project.past.db

Build docker container
docker build -t project.past.db .

Start docker container
docker run -v "$PWD":/usr/src -p 5432:5432 -e POSTGRES_PASSWORD=postgres --name project.past.db project.past.db

Init past project db
docker exec -it project.past.db -h localhost -p 5432 -U postgres -d postgres -f /usr/src/ddl/init_db.sql
