IMAGE_REGISTRY ?= ger-is-registry.caas.intel.com/cno/
BUILD_VERSION ?= v2.2.1

export NODUS_IMAGE_NAME ?= $(IMAGE_REGISTRY)ovn4nfv-k8s-plugin:$(BUILD_VERSION)

DOCKERARGS?=
ifdef HTTP_PROXY
	DOCKERARGS += --build-arg http_proxy=$(HTTP_PROXY)
endif
ifdef HTTPS_PROXY
	DOCKERARGS += --build-arg https_proxy=$(HTTPS_PROXY)
endif

docker-build:
	docker build -t $(NODUS_IMAGE_NAME) $(DOCKERARGS) --network host -f ./debian/Dockerfile .

docker-push:
	docker push $(NODUS_IMAGE_NAME)


