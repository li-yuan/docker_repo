include env_make
NS = hly
VERSION ?= 9.6

REPO = postgresql
NAME = postgresql
INSTANCE = default

.PHONY: build push shell run start stop rm release test

build:
	docker build -t $(NS)/$(REPO):$(VERSION) .

push:
	docker push $(NS)/$(REPO):$(VERSION)

shell:
	docker run --rm --name $(NAME)-$(INSTANCE) -i -t $(PORTS) $(VOLUMES) $(ENV) $(NS)/$(REPO):$(VERSION) /bin/bash

run:
	docker run --rm --name $(NAME)-$(INSTANCE) $(PORTS) $(VOLUMES) $(ENV) $(NS)/$(REPO):$(VERSION)

start:
	docker run -d --name $(NAME)-$(INSTANCE) $(PORTS) $(VOLUMES) $(ENV) $(NS)/$(REPO):$(VERSION)

stop:
	docker stop $(NAME)-$(INSTANCE)

rm:
	docker rm $(NAME)-$(INSTANCE)

test:
	docker run -it --rm --link $(NAME)-$(INSTANCE):$(DB_NAME) $(NS)/$(REPO):$(VERSION) psql -h $(DB_NAME) -U $(PG_USERNAME)

release: build
	make push -e VERSION=$(VERSION)

default: build 
