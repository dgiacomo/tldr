# bazel test

> https://bookstack.mux.io/books/developer-environment/page/bazel-cheatsheet

- Run a single test : `--test-filter` with a regex to the test you want : Example: `^MyTest*` or `MyTest` 

`./bazel.sh test --test_filter='{{regex}}' {{path}}`

- Get verbose test output : lists all tests run and how long they took

`./bazel.sh test --test_arg="-test.v" --test_output=all {{path}}`

- Investigate flaky tests : re-run a test _N_ times, **concurrently**, only keeping logs from failing tests. (Use **--local_test_jobs=1** to run sequentially). **Warning:** cached test results will be used for all tests that are not _external_ if **--cache_test_results=yes**.

`./bazel.sh test --runs_per_test={{num}} --nocache_test_results {{path}}`
