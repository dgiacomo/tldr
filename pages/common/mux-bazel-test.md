# bazel test

> https://bookstack.mux.io/books/developer-environment/page/bazel-cheatsheet

- Run a single test : `--test-filter` with a regex to the test you want : Example: `^MyTest*` or `MyTest` 

`./bazel.sh test --test_filter='{{regex}}' {{path}}`

- Get verbose test output; lists all tests run and how long they took

`./bazel.sh test --test_arg="-test.v" --test_output=all {{path}}`

