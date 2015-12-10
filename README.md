# docker-go-gb
For using gb build and fetch for go applications

# Build the image
```bash
$ docker build -t <user>/<repo>:<version> .
```

# Example use case if the image is built and pushed into a repo
```bash
$ cd "$GO_REPO"
$ docker run --rm -it -v "$PWD":/go -w /go quay.io/ukhomeofficedigital/go-gb:1.0.0 gb build all
```

# To cross compile a Go program (supported in go 1.5)

- Find the GOOS and GOARCH environment variables for the target [operating system and architecture](http://golang.org/doc/install/source#environment)
- Run the container and pass the variables - below is an example for cross compiling to darwin amd64 (for Mac OSX)
```bash
$ docker run --rm -it -e GOOS=darwin -e GOARCH=amd64 -v "$PWD":/go -w /go quay.io/ukhomeofficedigital/go-gb:1.0.0 gb build all
```
