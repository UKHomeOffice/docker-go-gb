# docker-go-gb
For using gb build and fetch for go applications

# Build the image
docker build -t <user>/<repo>:<version> .

# Example use case if the image is built and pushed into a repo
cd "$GO_REPO"
docker run --rm -it -v "$PWD":/go -w /go quay.io/ukhomeofficedigital/go-gb:1.0.0 gb build all
