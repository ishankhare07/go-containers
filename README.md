#### Running
The included docker-compose file defines a linux container service that
acts as a sandbox for running our toy container implementation. This is necessary
because certain `clone flags` are only available under linux. The toy container runs a fully
functional `alpine linux` container.

1. Start the linux container with `docker-compose run linux`
2. Build the go code with `go build contained.go`. This will give the contained binary.
3. Run the toy container with any command `./contained run /bin/sh`

This toy container runs with its own root filesystem as well as a mounted `/proc` hence running
commands like `ps` inside the toy container will only show processes running inside the toy container
