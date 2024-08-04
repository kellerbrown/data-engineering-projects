SCALE ?= 2

build:
	@docker compose build

down:
	@docker compose down --volumes --remove-orphans

run:
	@make down && docker compose up

run-scaled:
	@make down && docker compose up --scale spark-worker=$(SCALE)

stop:
	@docker compose stop

get-version:
	@docker exec spark-master spark-submit --master spark://spark-master:7077 --deploy-mode client --version

submit:
	@docker exec spark-master spark-submit --master spark://spark-master:7077 --deploy-mode client ./apps/$(APP)