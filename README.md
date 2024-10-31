# Microservices Proto

This Repo is based on https://github.com/huseyinbabal/microservices-proto/tree/main

## Dependencies

 ### Stubs Generation Protoc
 ```
 # Mac
 brew install protobuf
 protoc --version  # Ensure compiler version is 3+
 # Linux
 apt install -y protobuf-compiler
 protoc --version  # Ensure compiler version is 3+
 ```

### Protoc Dependencies to generate source code specific to the Go language
Install the next dependencies
```
go install google.golang.org/protobuf/cmd/protoc-gen-go@latest
go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@latest
```

## Creation of Stubs

### GO
```
protoc --go_out=./golang --go-grpc_out=./golang --go_opt=paths=source_relative --go-grpc_opt=paths=source_relative order/order.proto
# Steps for creating go module
go mod init github.com/jsanchezmen/microservices-proto/golang/{service}
go mod tidy
```

## Import

```
go get -u github.com/huseyinbabal/microservices-proto/golang/order@v1.2.3
```
