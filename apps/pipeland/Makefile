
.PHONY: app container push run

all: app container clean

app: .
	npm install
	npm run-script build

container: .
	cd $(shell pwd)/.. && docker build -f pipeland/Dockerfile -t streamkitchen/pipeland .

# Development container that can be easily spun up while working.
dev: .
	npm run-script build
	docker build -f Dockerfile.dev -t streamkitchen/pipeland-dev .

push: .
	docker push streamkitchen/pipeland

clean: .
	mkdir -p dist
	rm -rf dist
