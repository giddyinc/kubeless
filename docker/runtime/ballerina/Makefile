init-image:
	docker build -f Dockerfile.init -t kubeless/ballerina-init:0.980.0 .

runtime-image:
	env GOOS=linux GOARCH=amd64 go build $$GOPATH/src/github.com/kubeless/kubeless/pkg/function-proxy/proxy.go
	docker build -f Dockerfile -t kubeless/ballerina:0.980.0 .

push-init:
	docker push ballerina/kubeless-ballerina-init:0.980.0

push-runtime:
	docker push ballerina/kubeless-ballerina:0.980.0

# Mandatory jobs
build-all: init-image runtime-image
push-all: push-init push-runtime
