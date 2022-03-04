# bazel build and test

> https://bookstack.mux.io/books/developer-environment/page/bazel-cheatsheet

- Copy generated protos to your source tree so they appear for your IDE / go tools:

`./run/dev/scripts/copy-generated-protos.sh`

- Clean up protos copied to your source tree (used when they are interfering with Gazelle):

`./run/dev/scripts/copy-generated-protos.sh clean`

- Exclude a path in a build

`./bazel.sh build -- //video/... -//video/internal/servers/node-repoman/...`

- Clean : deletes output directories and resets internal caches

`./bazel.sh clean`

- Full Clean : completely removes the entire working tree and shuts down server to clear memory  

`./bazel.sh clean --expunge`

