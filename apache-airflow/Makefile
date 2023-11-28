up: .env .initialized
	docker-compose --profile flower up -d

down:
	docker-compose --profile flower down

clean:
	docker compose --profile flower down --volumes --remove-orphans
	rm -rf .env .initialized config logs plugins

.initialized:
	docker-compose up airflow-init
	touch .initialized

.env:
	echo "AIRFLOW_UID=$$(id -u)" > .env
