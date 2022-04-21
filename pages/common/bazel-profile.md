# bazel profile

> https://bookstack.mux.io/books/developer-environment/page/bazel-cheatsheet#bkmrk-profiling-bazel

- **Profile a build**  : `--profile` : output has microsecond timing and is in json format - filenames with `.gz` extension will be compressed 

`./bazel.sh build {{path}} --profile={{file}}{{.gz}}`

- **Perfetto Analysis Tool** : https://ui.perfetto.dev/ : SQL : *Time taken for each external dependency in seconds, sorted*

`select dur / 1000000 as sec, name from slice where name like "%external%" order by dur desc`

- **Perfetto Analysis Tool** : https://ui.perfetto.dev/ : SQL : *All Bazel actions, sorted by duration:*

`select dur, name from slice order by dur desc`

- **Commandline Analysis**: *Use bazel to generate a summary of the previosuly captured profile data* : `analyze-profile`

`./bazel.sh analyze-profile {{file}}`

- **Analyze uncompressed profile data with jq** : *List events that took longer than 20 seconds*:

`jq -e '.traceEvents[] | select(.dur > 20000000) | [.dur, .name] | join(" ")' {{file}} | sort`
