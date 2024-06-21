# Example Makefile for creating the docker image

.PHONY: build push deploy devinstall pullpushsub

REG:="eclecticiq"
IMAGE:="opentaxii"

all: build push

build:
	docker  build -t $(REG)/$(IMAGE) ../.

push:
	docker push $(REG)/$(IMAGE) ../.

deploy:
	docker compose up -d --build

devinstall:
	python3 -m venv ../venv && \
	. ../venv/bin/activate && \
	pip install -r requirements-dev.txt

pullpushsub:
	. ../.venv/bin/activate && \
	python3 pullpushsub.py
