# bazel

> More information: <https://bazel.build/>

- See what uses the dependency "org_golang_x_crypto" across entire repo: 

`./bazel.sh query "deps({{//path...}})" --output graph | grep {{dependency}}`   # Note: dependency is of form as represented by Bazel "org_golang_x_crypto"

- Add or update dependency "github.com/spf13/cobra" to the WORKSPACE (default: latest or specify version with "@v1.2.1"): 

`./bazel.sh run //:gazelle update-repos {{dependency}}`       

- Update WORKSPACE with the contents of the go.mod file : Note it has to be named go.mod

`./bazel.sh run //:gazelle -- update-repos -from_file=go.mod`
  
- Full Clean

`./bazel.sh clean --expunge`

- Copy generated protos to your source tree so they appear for your IDE / go tools:

`./run/dev/scripts/copy-generated-protos.sh`

- Clean for the above copied files (if they are interfering with Gazelle):

`./run/dev/scripts/copy-generated-protos.sh clean`

- Get a sorted list of all the dependencies used by "path" : path is expanded to "//path/..." : (video, data, run)

`./run/dev/scripts/query_dependencies.sh {{path}}` 

- Run a single test - use `--test-args=run=<regex>`

`./bazel.sh test --test_arg=--test.run='^TestLiveStreamDelete*' //video/internal/services/assetindex/...`

## Build 

- Build, but exclude a path

`./bazel.sh build -- //video/... -//video/internal/servers/node-repoman/...`

- Regenerate BUILD files - useful after changing dependencies

`./bazel.sh run //:gazelle`
