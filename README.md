# Base monorepo

Base monorepo for go and python development using Bazel for building. Only dependency is [Bazelisk](https://github.com/bazelbuild/bazelisk).

Somme examples are provided for:

* Building a basic go "hello world" with external dependencies
* Building a basic python "hello world"
* Buidling a basic GRPC "hello world"
* How built apps could be deployed locally using docker compose

## Usage
Update go.mod for whole repo (at the root): `go mod tidy`

Auto-generate all BUILD files for go code: `bazel run //:gazelle`

Auto-download all go dependencies from go.mod: `bazel run //:gazelle-update-repos`

Build all: `bazel build //...`

Build target: `bazel build //examples/hello_world:hello_world`

Run tests: `bazel test //... --test_output=errors`

Docker compose build: `docker compose build`

Docker compose run: `docker compose up -d`
