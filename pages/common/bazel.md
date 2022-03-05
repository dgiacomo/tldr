# bazel

> https://bookstack.mux.io/books/developer-environment/page/bazel-cheatsheet

- What uses a dependency in the path (dependency format is "org_golang_x_crypto", use path '//...' to scan the full repo)

`./bazel.sh query "deps({{path}})" --output graph | grep {{dependency}}`   

- Add or update dependency in WORKSPACE. Doesn't handle transitives. Pulls latest if version not specified : {{dependency}}@v{{version}} example: github.com/spf13/cobra@v1.2.1

`./bazel.sh run //:gazelle update-repos {{dependency}}`       

- Use a go.mod file to update contents of WORKSPACE. Adds to or updates entries that leverage sum + version : Note: file has to be named go.mod

`./bazel.sh run //:gazelle -- update-repos -from_file=go.mod`
  
- Get a sorted list of all the dependencies used by "path" : path is expanded to "//path/..." : (video, data, run or all if no arg is provided)

`./run/dev/scripts/query_dependencies.sh {{path}}` 

- Regenerate BUILD files after changing dependencies : path is optional but can be used to limit to the area you were working in

`./bazel.sh run //:gazelle {{path}}`

- Copy generated protos to your source tree : for IDE / go tooling

`./run/dev/scripts/copy-generated-protos.sh`

- Clean up protos copied to your source tree (used when they are interfering with Gazelle):

`./run/dev/scripts/copy-generated-protos.sh clean`
