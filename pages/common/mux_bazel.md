# bazel

> More information: TODO: Change this to a bookstack page

- See what uses a dependency in the repo path (dependency format is "org_golang_x_crypto", use path '//...' to scan the full repo). Example: `bazel.sh`

`./bazel.sh query "deps({{path}})" --output graph | grep {{dependency}}`   

- Add or update dependency "github.com/spf13/cobra" to the WORKSPACE (default: latest or specify version with "@v1.2.1"): 

`./bazel.sh run //:gazelle update-repos {{dependency}}`       

- Update WORKSPACE with the contents of the go.mod file : Note it has to be named go.mod

`./bazel.sh run //:gazelle -- update-repos -from_file=go.mod`
  
- Get a sorted list of all the dependencies used by "path" : path is expanded to "//path/..." : (video, data, run)

`./run/dev/scripts/query_dependencies.sh {{path}}` 

- Regenerate BUILD files - useful after changing dependencies

`./bazel.sh run //:gazelle`
