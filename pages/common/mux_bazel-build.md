# bazel build and test

> More information: TODO: Change this to a bookstack page

- Copy generated protos to your source tree so they appear for your IDE / go tools:

`./run/dev/scripts/copy-generated-protos.sh`

- Clean up protos copied to your source tree (used when they are interfering with Gazelle):

`./run/dev/scripts/copy-generated-protos.sh clean`

- Run a single test use `--test-filter` with a regex to the test you want. : Example: `^MyTest*` or `MyTest` 

`./bazel.sh test --test_filter='{{regex}}' {{path}}`

- Get verbose test output, like all tests run and how long they took

`./bazel.sh test --test_arg="-test.v" --test_output=all {{path}}`

- Build, but exclude a path

`./bazel.sh build -- //video/... -//video/internal/servers/node-repoman/...`

- Clean : deletes output directories and resets internal caches

`./bazel.sh clean`

- Full Clean : completely removes the entire working tree and shuts down server to clear memory  

`./bazel.sh clean --expunge`

- Investigate a failed build / test TODO: use sandbox debug and describe how to use it 

`./bazel.sh {{build|test}} `
