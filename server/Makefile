postgresinit:
	docker run --name realtime-chat -p 4444:5432 -e POSTGRES_USER=root -e POSTGRES_PASSWORD=123456 -d postgres:15.4

postgres:
	docker exec -it realtime-chat psql

createdb:
	docker exec -it realtime-chat createdb --username=root --owner=root realtime-chat

migrateup:
	migrate -path db/migrations -database "postgresql://root:123456@localhost:4444/realtime-chat?sslmode=disable" -verbose up

migratedown:
	migrate -path db/migrations -database "postgresql://root:123456@localhost:4444/realtime-chat?sslmode=disable" -verbose down

dropdb:
	docker exec -it realtime-chat dropdb realtime-chat

.PHONY: postgresinit postgres createdb dropdb



