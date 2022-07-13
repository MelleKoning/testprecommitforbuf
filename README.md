# Hello world

This repository is setup to test the buf linter with pre-commit

## what is the issue

when running

```bash
buf lint
```

the output properly gives a few warnings about the `api/td1.proto` file:

```bash
api/td1.proto:3:1:Files with package "td1" must be within a directory "td1" relative to root but were in directory "api".
api/td1.proto:3:1:Package name "td1" should be suffixed with a correctly formed version, such as "td1.v1".
api/td1.proto:20:9:Service name "TD1" should be suffixed with "Service".
api/td1.proto:23:22:RPC request type "HealthInfoRequest" should be named "GetHealthRequest" or "TD1GetHealthRequest".
api/td1.proto:23:50:RPC response type "HealthInfoResponse" should be named "GetHealthResponse" or "TD1GetHealthResponse".
```

however when running

```bash
pre-commit run -a
```

the output skips the buf linter, and the output is:

```bash
trim trailing whitespace.................................................Passed
fix end of files.........................................................Passed
check yaml...............................................................Passed
check for added large files..............................................Passed
check json...........................................(no files to check)Skipped
pretty format json...................................(no files to check)Skipped
check for merge conflicts................................................Passed
check for broken symlinks............................(no files to check)Skipped
detect private key.......................................................Passed
don't commit to branch...................................................Passed
mixed line ending........................................................Passed
golangci-lint............................................................Passed
markdownlint-fix.........................................................Passed
buf lint.............................................(no files to check)Skipped
```
