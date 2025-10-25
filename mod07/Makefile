.PHONY: build
build:
	docker build --tag myscratchimage .

# Have to authenticate to dockerhub and create repo first:
# https://docs.docker.com/engine/reference/commandline/login/
.PHONY: push-dockerhub
push-dockerhub:
	docker tag my-scratch-image tybennett/myscratchimage # defaults to latest
	docker push tybennett/myscratchimage

	docker tag myscratchimage tybennett/myscratchimage:abc-123
	docker push tybennett/myscratchimage:abc-123

# Have to authenticate to ghcr.io first
# https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-container-registry#authenticating-to-the-container-registry
.PHONY: push-github-packages
push-github-packages:
	docker tag myscratchimage ghcr.io/ty-bennett/myscratchimage # defaults to latest
	docker push ghcr.io/ty-bennett/myscratchimage

	docker tag myscratchimage ghcr.io/ty-bennett/myscratchimage:abc-123 # defaults to latest
	docker push ghcr.io/ty-bennett/myscratchimage:abc-123
