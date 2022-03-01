# bazel

> More information: <https://bazel.build/>.

- See what uses the dependency "org_golang_x_crypto" across entire repo: 

`./bazel.sh query "deps(//...)" --output graph | grep org_golang_x_crypto`

- Update the dependency "github.com/spf13/cobra" (to latest): 

`./bazel.sh run //:gazelle update-repos github.com/spf13/cobra`

- Update the dependency "github.com/spf13/cobra" to version "v1.2.1": 

`./bazel.sh run //:gazelle update-repos github.com/spf13/cobra@v1.2.1`

- Add the new dependency "github.com/juju/errors" to the WORKSPACE

`./bazel.sh run //:gazelle update-repos github.com/juju/errors`

- Full Clean

`./bazel.sh clean --expunge`

- Copy generated protos to your source tree so they appear for your IDE / go tools:

`run/dev/scripts/copy-generated-protos.sh`

- Clean for the above copied files (if they are interfering with Gazelle):

`run/dev/scripts/copy-generated-protos.sh clean`

- Get a sorted list of all the dependencies used by "//video/..."

`./run/dev/scripts/query_dependencies.sh video`
