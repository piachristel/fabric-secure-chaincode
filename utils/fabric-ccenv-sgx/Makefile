.PHONY: all

all: prep build

prep: 
	git clone https://github.com/tozd/docker-sgx.git 
	cd docker-sgx && git checkout 08c2457 && ln -s ubuntu-xenial.dockerfile Dockerfile && git apply ../sgx_2.4.patch

build:
	docker build -t hyperledger/fabric-ccenv-sgx:latest docker-sgx

clean:
	rm -rf docker-sgx
